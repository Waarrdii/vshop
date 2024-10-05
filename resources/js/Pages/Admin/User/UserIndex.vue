<script setup>
import AdminLayout from '@/Layouts/AdminLayout.vue';
import { Head } from '@inertiajs/vue3';
import TableComponent from '@/Components/TableComponent.vue';
import TableHeader from '@/Components/TableHeader.vue';
import TableRow from '@/Components/TableRow.vue';
import TableData from '@/Components/TableData.vue';

defineProps(['users'])
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <h1>User List</h1>
            <div class="mt-6">
                <TableComponent>
                    <template #header>
                        <TableRow>
                            <TableHeader>ID</TableHeader>
                            <TableHeader>Name</TableHeader>
                            <TableHeader>Email</TableHeader>
                            <TableHeader>Action</TableHeader>
                        </TableRow>
                    </template>
                    <template #default>
                        <TableRow v-for="user in users" :key="user.id" class="border-b">
                            <TableData>{{ user.id }}</TableData>
                            <TableData>{{ user.name }}</TableData>
                            <TableData>{{ user.email }}</TableData>
                            <TableData>Edit/Delete</TableData>
                        </TableRow>
                    </template>
                </TableComponent>
            </div>
        </div>
    </AdminLayout>
</template>

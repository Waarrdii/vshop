<script setup>
import AdminLayout from '@/Layouts/AdminLayout.vue';
import { Head } from '@inertiajs/vue3';
import TableComponent from '@/Components/TableComponent.vue';
import TableHeader from '@/Components/TableHeader.vue';
import TableRow from '@/Components/TableRow.vue';
import TableData from '@/Components/TableData.vue';

defineProps(['permissions'])
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <h1>Permissions List</h1>
            <div class="mt-6">
                <TableComponent>
                    <template #header>
                        <TableRow>
                            <TableHeader>ID</TableHeader>
                            <TableHeader>Name</TableHeader>
                            <TableHeader>Action</TableHeader>
                        </TableRow>
                    </template>
                    <template #default>
                        <TableRow v-for="item in permissions" :key="item.id" class="border-b">
                            <TableData>{{ item.id }}</TableData>
                            <TableData>{{ item.name }}</TableData>
                            <TableData>Edit/Delete</TableData>
                        </TableRow>
                    </template>
                </TableComponent>
            </div>
        </div>
    </AdminLayout>
</template>

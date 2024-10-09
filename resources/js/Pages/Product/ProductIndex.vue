<script setup>
import AdminLayout from '@/Layouts/AdminLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
import TableComponent from '@/Components/TableComponent.vue';
import TableHeader from '@/Components/TableHeader.vue';
import TableRow from '@/Components/TableRow.vue';
import TableData from '@/Components/TableData.vue';

defineProps(['products'])
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <div class="flex justify-between">
                <h1>Product List</h1>
                <Link :href="route('products.create')" class="text-white bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2 ">Add Product</Link>
            </div>
            
            <div class="mt-6">
                <TableComponent>
                    <template #header>
                        <TableRow>
                            <TableHeader>ID</TableHeader>
                            <TableHeader>Name</TableHeader>
                            <TableHeader>Brand</TableHeader>
                            <TableHeader>Category</TableHeader>
                        </TableRow>
                    </template>
                    <template #default>
                        <TableRow v-for="item in products" :key="item.id" class="border-b">
                            <TableData>{{ item.id }}</TableData>
                            <TableData>{{ item.name }}</TableData>
                            <TableData>{{ item.brand }}</TableData>
                            <TableData>{{ item.category }}</TableData>
                        </TableRow>
                    </template>
                </TableComponent>
            </div>
        </div>
    </AdminLayout>
</template>

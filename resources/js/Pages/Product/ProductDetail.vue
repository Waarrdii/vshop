<script setup>
import AdminLayout from '@/Layouts/AdminLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

const form = useForm( {
    name:"",
    brand:"",
    category:"",
    image_url:"",
}
    
)

</script>

<template>
    <Head title="Create New Product" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <div class="flex justify-between">
                <h1>Product</h1>
                <Link :href="route('products.index')" class="text-white bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2 ">Back</Link>
            </div>
            
            <div class="mt-6">
                <form @submit.prevent="form.post(route('products.store'))">
            <div>
                <InputLabel for="name" value="Name" />

                <TextInput
                    id="name"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.name"
                    autofocus
                />

                <InputError class="mt-2" :message="form.errors.name" />
            </div>
            
            <div>
                <InputLabel for="brand" value="Brand" />

                <TextInput
                    id="brand"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.brand"
                    autofocus
                />

                <InputError class="mt-2" :message="form.errors.name" />
            </div>
            <div>
                <InputLabel for="category" value="Category" />

                <TextInput
                    id="category"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.category"
                    autofocus
                />

                <InputError class="mt-2" :message="form.errors.name" />
            </div>
            <div>
                <InputLabel for="image_url" value="image_url" />

                <TextInput
                    id="image_url"
                    type="text"
                    class="mt-1 block w-full"
                    v-model="form.image_url"
                    autofocus
                />

                <InputError class="mt-2" :message="form.errors.name" />
            </div>
            

            <div class="mt-4 flex items-center justify-end">
                <PrimaryButton
                    class="ms-4"
                    :class="{ 'opacity-25': form.processing }"
                    :disabled="form.processing"
                >
                    Create
                </PrimaryButton>
            </div>
        </form>
            </div>
        </div>
    </AdminLayout>
</template>

<template>
    <Head title="Create Product"></Head>
    <FrontendLayout>
        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Create Product</h5>
                <Link
                    :href="route('products.index')"
                    class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4"
                    >Back To Home</Link
                >
            </div>
            <form @submit.prevent="saveProduct()">
                <div class="grid grid-cols-12 gap-4">
                    <div class="col-span-6">
                        <div class="mb-6">
                            <label
                                class="block text-sm font-medium text-gray-700"
                                >Product Name</label
                            >
                            <input
                                type="text"
                                v-model="form.name"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                            />
                            <div
                                v-if="errors.name"
                                class="mt-2 text-sm text-red-600"
                            >
                                {{ errors.name }}
                            </div>
                        </div>
                        <div class="mb-6">
                            <label
                                class="block text-sm font-medium text-gray-700"
                                >Product Price</label
                            >
                            <input
                                type="text"
                                v-model="form.price"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                            />
                            <div
                                v-if="errors.price"
                                class="mt-2 text-sm text-red-600"
                            >
                                {{ errors.price }}
                            </div>
                        </div>
                        <div class="mb-3">
                            <Link
                                :href="route('products.index')"
                                class="bg-red-600 text-white py-2 px-5 rounded mb-4 inline-block mr-2"
                            >
                                Back
                            </Link>
                            <button
                                type="submit"
                                :disabled="form.processing"
                                class="bg-blue-500 text-white py-2 px-5 rounded mb-4"
                            >
                                <span v-if="form.processing">Save....</span>
                                <span v-else>Save</span>
                            </button>
                        </div>
                    </div>
                </div>
            </form>
        </div>
    </FrontendLayout>
</template>

<script setup>
import FrontendLayout from "@/Layouts/FrontendLayout.vue";
import { Head, Link, useForm } from "@inertiajs/vue3";

defineProps({ errors: Object });

const form = useForm({
    name: "",
    price: "",
});

const saveProduct = () => {
    const res = form.post(route("products.store"));
    if (res) {
        form.reset();
    }
};
</script>

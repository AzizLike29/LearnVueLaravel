<template>
    <Head title="Edit Product"></Head>
    <FrontendLayout>
        <div v-if="$page.props.flash.message" class="alert">
            {{ $page.props.flash.message }}
        </div>
        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Edit Product</h5>
                <Link
                    :href="route('products.index')"
                    class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4"
                    >Back To Home</Link
                >
            </div>
            <form @submit.prevent="updateProduct()">
                <div class="grid grid-cols-12 gap-4">
                    <div class="col-span-6">
                        <div class="mb-3">
                            <label>Product Name</label>
                            <input
                                type="text"
                                v-model="form.name"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                            />
                            <div v-if="errors.name" class="text-red-500">
                                {{ errors.name }}
                            </div>
                        </div>
                        <div class="mb-3">
                            <label>Product Price</label>
                            <input
                                type="text"
                                v-model="form.price"
                                class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                            />
                            <div v-if="errors.price" class="text-red-500">
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
                                <span v-if="form.processing">Updating....</span>
                                <span v-else>Update</span>
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

const props = defineProps({ errors: Object, product: Object });

const form = useForm({
    name: props.product.name,
    price: props.product.price,
});

const updateProduct = () => {
    const res = form.put(route("products.update", props.product.id));
    if (res) {
        form.reset();
    }
};
</script>

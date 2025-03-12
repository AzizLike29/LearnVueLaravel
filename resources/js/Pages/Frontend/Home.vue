<template>
    <Frontend>
        <div
            class="w-full h-screen bg-[url('https://www.khueapps.com/media/images/2025-02/3.webp')] bg-cover bg-center"
        >
            <div
                class="w-full h-full flex flex-col justify-center items-center backdrop-blur-md"
            >
                <Head title="Home Page"></Head>
                <div class="flex flex-col items-center justify-center p-6">
                    <h1
                        class="text-6xl font-bold text-white mb-8 animate-fade-in"
                    >
                        Welcome to Our Website
                    </h1>
                    <p
                        class="text-lg text-white mb-12 max-w-2xl text-center animate-fade-in"
                    >
                        Discover amazing products and services tailored just for
                        you. Explore our collection and find what you need.
                    </p>
                    <button
                        @click="goToProduct"
                        class="bg-blue-600 text-white py-3 px-6 rounded-lg shadow-lg hover:bg-blue-700 transition-all duration-300 ease-in-out transform hover:scale-105 animate-bounce-in"
                    >
                        Explore Products
                    </button>
                    <div
                        class="mt-16 grid grid-cols-1 md:grid-cols-3 gap-8 animate-fade-in-up"
                    >
                        <div
                            class="bg-white/80 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 backdrop-blur-sm"
                        >
                            <h2
                                class="text-xl font-semibold text-gray-800 mb-4"
                            >
                                Feature One
                            </h2>
                            <p class="text-gray-600">
                                Lorem ipsum dolor sit amet, consectetur
                                adipiscing elit. Sed do eiusmod tempor
                                incididunt ut labore et dolore magna aliqua.
                            </p>
                        </div>
                        <div
                            class="bg-white/80 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 backdrop-blur-sm"
                        >
                            <h2
                                class="text-xl font-semibold text-gray-800 mb-4"
                            >
                                Feature Two
                            </h2>
                            <p class="text-gray-600">
                                Ut enim ad minim veniam, quis nostrud
                                exercitation ullamco laboris nisi ut aliquip ex
                                ea commodo consequat.
                            </p>
                        </div>
                        <div
                            class="bg-white/80 p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 backdrop-blur-sm"
                        >
                            <h2
                                class="text-xl font-semibold text-gray-800 mb-4"
                            >
                                Feature Three
                            </h2>
                            <p class="text-gray-600">
                                Duis aute irure dolor in reprehenderit in
                                voluptate velit esse cillum dolore eu fugiat
                                nulla pariatur.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </Frontend>
</template>

<script setup>
import { Head, router } from "@inertiajs/vue3";
import Frontend from "@/Layouts/FrontendLayout.vue";
const goToProduct = () => {
    router.visit(route("products.create"));
};
</script>

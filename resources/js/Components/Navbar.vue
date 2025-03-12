<template>
    <nav class="flex justify-between p-4 bg-gray-200">
        <div class="text-lg">Navbar</div>
        <div>
            <ul class="flex gap-x-3 me-auto mb-lg-0">
                <li class="nav-item">
                    <Link class="text-dark" :href="route('myhome')">Home</Link>
                </li>
                <li class="nav-item">
                    <Link class="text-dark" :href="route('myabout')"
                        >About Us</Link
                    >
                </li>
                <li class="nav-item">
                    <Link class="text-dark" :href="route('mycontact')"
                        >Contact</Link
                    >
                </li>
            </ul>
        </div>
    </nav>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
</script>

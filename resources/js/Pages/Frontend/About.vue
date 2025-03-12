<template>
    <div>
        <Frontend>
            <Head title="About Me"></Head>
            <h1>This is {{ title }}</h1>
        </Frontend>
    </div>
</template>

<script setup>
import { Head } from "@inertiajs/vue3";
import Frontend from "@/Layouts/FrontendLayout.vue";
defineProps({
    title: String,
});
</script>

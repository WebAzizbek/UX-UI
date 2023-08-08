<template>
    <button class="site-btn">
        {{ title }}
    </button>
</template>

<script setup>
const { title } = defineProps({
    title: {
        required: true
    }
})
</script>

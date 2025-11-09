<template>
    <button class="bg-blue-500 px-4 py-2 rounded-lg cursor-pointer" @click="emit('customClick')">
        {{ props.label }}
    </button>
</template>

<script setup>
const emit = defineEmits(['customClick'])
const props = defineProps(['label'])
</script>

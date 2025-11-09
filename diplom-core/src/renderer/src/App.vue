<script setup>
import Button from './components/Button.vue'

function onCustomClick() {
    alert('НЕ ПОШЕЛ НАХУЙ!')
}

function onCustomClick2() {
    alert('ПОШЕЛ НАХУЙ!')
}
</script>

<template>
    <Button label="Кнопка" @custom-click="onCustomClick"/>
    <Button label="Кнопка 2" @custom-click="onCustomClick2" />
</template>

<template>
    <NMenu v-model:value="modelValue" :options="menuOptions" />
</template>

<script setup>
import DocumentAdd24Regular from '@vicons/fluent/DocumentAdd24Regular'
import Settings20Regular from '@vicons/fluent/Settings20Regular'
import Info20Regular from '@vicons/fluent/Info20Regular'
import DocumentSearch24Regular from '@vicons/fluent/DocumentSearch24Regular'
import { computed, h, ref } from 'vue'
import { menuOptionsKeys } from '../data/constants'

const props = defineProps({
    selected: {
        type: String,
        default: menuOptionsKeys.Settings,
    },
})

const emit = defineEmits({
    'update:selected': (selectedKey) => {
        for (const key in menuOptionsKeys) {
            if (selectedKey !== key) {
                return false
            }
        }

        return true
    },
})

const menuOptions = ref([
    {
        label: 'Загрузка документов',
        key: menuOptionsKeys.UploadDocuments,
        icon: () => h(DocumentAdd24Regular),
    },

    {
        label: 'Поиск информации',
        key: menuOptionsKeys.Searching,
        icon: () => h(DocumentSearch24Regular),
    },

    {
        label: 'Помощь',
        key: menuOptionsKeys.Help,
        icon: () => h(Info20Regular),
    },

    {
        label: 'Настройки',
        key: menuOptionsKeys.Settings,
        icon: () => h(Settings20Regular),
    },
])

const modelValue = computed({
    set(newValue) {
        emit('update:selected', newValue)
    },

    get() {
        return props.selected
    },
})
</script>

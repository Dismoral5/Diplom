<script setup>
import SearchForm from './components/SearchForm.vue'
import { darkTheme, useOsTheme } from 'naive-ui'
import { computed } from 'vue'
import DocumentAdd24Regular from '@vicons/fluent/DocumentAdd24Regular'
import DocumentSearch24Regular from '@vicons/fluent/DocumentSearch24Regular'
import Settings20Regular from '@vicons/fluent/Settings20Regular'
import Info20Regular from '@vicons/fluent/Info20Regular'
import Result from './components/Result.vue'

const osTheme = useOsTheme()
const theme = computed(() => (osTheme.value === 'dark' ? darkTheme : null))
</script>

<template>
    <NConfigProvider :theme="theme">
        <NSpace vertical>
            <NLayout has-sider class="h-lvh" embedded>
                <NLayoutSider>
                    <NList clickable hoverable :show-divider="false" :bordered="false">
                        <template #header> Опции </template>

                        <NListItem>
                            <template #prefix>
                                <NIcon size="24">
                                    <DocumentAdd24Regular />
                                </NIcon>
                            </template>
                            Загрузка документов
                        </NListItem>

                        <NListItem>
                            <template #prefix>
                                <NIcon size="24">
                                    <DocumentSearch24Regular />
                                </NIcon>
                            </template>
                            Поиск информации
                        </NListItem>

                        <NListItem>
                            <template #prefix>
                                <NIcon size="24">
                                    <Info20Regular />
                                </NIcon>
                            </template>
                            Помощь
                        </NListItem>

                        <NListItem>
                            <template #prefix>
                                <NIcon size="24">
                                    <Settings20Regular />
                                </NIcon>
                            </template>
                            Настройки
                        </NListItem>
                    </NList>
                </NLayoutSider>

                <NLayout>
                    <NLayoutContent content-class="p-4 h-full">
                        <Result />
                    </NLayoutContent>
                </NLayout>

                <NLayoutSider>
                    <SearchForm />
                </NLayoutSider>
            </NLayout>
        </NSpace>
    </NConfigProvider>
</template>

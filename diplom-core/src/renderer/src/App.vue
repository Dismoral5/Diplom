<script setup>
import SearchForm from './layout/SearchForm.vue'
import { darkTheme, useOsTheme } from 'naive-ui'
import { computed, ref } from 'vue'
import Result from './layout/Result.vue'
import Navigator from './components/Navigator.vue'
import { menuOptionsKeys } from './data/constants'

const selectedMenuItem = ref(menuOptionsKeys.Searching)

const osTheme = useOsTheme()
const theme = computed(() => (osTheme.value === 'dark' ? darkTheme : null))
</script>

<template>
    <NConfigProvider :theme="theme">
        <NSpace vertical>
            <NLayout has-sider class="h-lvh" embedded>
                <NLayoutSider>
                    <Navigator v-model:selected="selectedMenuItem" />
                </NLayoutSider>

                <NLayout>
                    <NLayoutContent content-class="p-4 h-full">
                        <Result v-if="selectedMenuItem === menuOptionsKeys.Searching" />
                    </NLayoutContent>
                </NLayout>

                <NLayoutSider v-if="selectedMenuItem === menuOptionsKeys.Searching">
                    <SearchForm />
                </NLayoutSider>
            </NLayout>
        </NSpace>
    </NConfigProvider>
</template>

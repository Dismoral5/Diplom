<template>
    <NCard :bordered="false">
        <template #header> Данные по помещению </template>

        <template #default>
            <NForm>
                <NFormItem label="Метраж">
                    <NInputNumber placeholder="Введите данные" :bordered="false" />
                </NFormItem>
            </NForm>
        </template>

        <template #action>
            <NButton tertiary>Проверить</NButton>
        </template>
    </NCard>
</template>

<script setup></script>

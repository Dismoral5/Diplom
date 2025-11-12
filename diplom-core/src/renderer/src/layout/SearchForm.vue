<template>
    <NCard :bordered="false">
        <template #header> Данные по помещению </template>

        <template #default>
            <NForm>
                <NFormItem label="Площадь помещения">
                    <NInputNumber placeholder="Введите данные" :bordered="false">
                        <template #suffix> м<sup>2</sup> </template>
                    </NInputNumber>
                </NFormItem>

                <NFormItem label="Толщина стен">
                    <NInputNumber placeholder="Введите данные" :bordered="false">
                        <template #suffix> м </template>
                    </NInputNumber>
                </NFormItem>

                <NFormItem label="Наличие САЗ">
                    <NSpace>
                        <NCheckbox label="Да" />
                        <NCheckbox label="Нет" />
                    </NSpace>
                </NFormItem>

                <NFormItem label="Перечень документов для работы Кгр">
                    <NSelect multiple :bordered="false" placeholder="Выберите из списка" />
                </NFormItem>
            </NForm>
        </template>

        <template #action>
            <NButton tertiary>Проверить </NButton>
        </template>
    </NCard>
</template>

<script setup>
import { NCheckbox, NForm, NFormItem } from 'naive-ui'
</script>

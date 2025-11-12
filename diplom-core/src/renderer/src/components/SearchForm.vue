<template>
    <NCard :bordered="false">
        <template #header> Данные по помещению </template>

        <template #default>
                <NForm>
                    <NFormItem label="Площадь помещения">
                        <NInputNumber  placeholder="Введите данные" :bordered="false" />
                    </NFormItem>
                </NForm>
                <NForm>
                    <NFormItem label="Толщина стен">
                        <NInputNumber  placeholder="Введите данные" :bordered="false" />
                    </NFormItem>
                </NForm>
                <NForm>
                    <NFormItem label="Наличие САЗ">
                        <input type="checkbox" id="yes" name="yes" aria-checked="true" :bordered="false" />
                        <label for="yes">Да</label>
                        <input type="checkbox" id="no" name="no" aria-checked="true" :bordered="false" />
                        <label for="no">Нет</label>
                    </NFormItem>
                </NForm>
                <NForm>
                    <NFormItem label="Перечень документов для работы Кгр">
                        <NInput  placeholder="Введите данные" :bordered="false" />
                    </NFormItem>
                </NForm>
           
        </template>

        <template #action>
            <NButton tertiary >Проверить </NButton>
        </template>
    </NCard>
</template>

<script setup>
import { NCheckbox, NCheckboxGroup, NForm, NFormItem, NInput, NInputGroupLabel, NInputOtp, NMenu } from 'naive-ui';

</script>

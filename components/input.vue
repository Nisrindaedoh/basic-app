<script setup>
import { stringify } from 'postcss';

const props = defineProps({
    id: {
        type: String,
        default: "text",
    },
    name: {
        type: String,
        default: "text",
    },
    classStyle: {
        type: String,
        default: "w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600"
    },
    type: {
        type: String,
        default: "text",
    },
    placeholder: {
        type: String,
        default: "Enter name",
    },
    value: {
        type: String,
    },
    onChange: {
        type: Function,
    },
});

const onChange = (e) => {
    props.onChange(e.target.value, props.name);
};

</script>
<template>
    <input 
        :class="props.classStyle" 
        :type="props.type" 
        :placeholder="props.placeholder" 
        v-model="props.value"
        @change="onChange" 
    />
</template>


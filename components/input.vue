<script setup>
const props = defineProps({
    id: {
        type: String,
        default: "text",
    },
    name: {
        type: String,
        default: "text",
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
    <input class="w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600" 
    :type="props.type"
    :placeholder="props.placeholder" 
    v-model="props.value" 
    @change="onChange" />
</template>


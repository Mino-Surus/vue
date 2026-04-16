<script setup>
const props = defineProps({
    msg: String,
    default: "",
    num: {
        type: String,
        required: true,
        default: () => {
            return "example@mail.ru"
        },
        validator: (value) => {
        value.length > 5 && value.includes('@')
        }
    }
})
</script>

<template>
    <p>{{num}}</p>
</template>
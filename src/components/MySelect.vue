<template>
    <select class="header__filter cs-filter" v-model="modelValue" @change="changeOption">
        <option disabled value="">Выберите из списка</option>
        
        <option 
            v-for="option in options"
            :key="option.value" 
            :value="option.value"
        >
            {{ option.name }}
        </option>

    </select>
</template>

<script>
export default {
    props: {
        modelValue: {
            type: String
        },
        options: {
            type: Array,
            default: () => [] 
        }
    },
    methods: {
        changeOption(event) {
            this.$emit('update:modelValue', event.currentTarget.value)
        }
    }
}
</script>

<style>

</style>
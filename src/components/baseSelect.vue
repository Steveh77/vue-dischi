<template>
    <select v-model="selected" @change="changeOption">
        <option value="">Seleziona un genere:</option>
        <option v-for="option in options" :key="option.value || option" :value="option.value || option">{{
                option.label || option
        }}</option>
    </select>
</template>

<script>
export default {
    name: "baseSelect",
    data() {
        return {
            selected: ""
        }
    },
    props: {
        options: Array
    },
    methods: {
        changeOption() {
            this.$emit("option-change", this.selected)
        }
    },
}
</script>

<style>
</style>
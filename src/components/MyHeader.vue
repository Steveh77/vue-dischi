<template>
    <nav>
        <i class="fa-brands fa-spotify"></i>
        <div>
            <BaseSelect :options="genersList" @option-change="emitGenreChange" />

        </div>
    </nav>
</template>

<script>
import BaseSelect from './baseSelect.vue'
export default {
    props: {
        genersList: Array
    },
    components: { BaseSelect },
    methods: {
        emitGenreChange(genre) {
            this.$emit("genre-change", genre)
        }
    },
}
</script>

<style lang="scss" scoped>
nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100px;
    background-color: rgb(46, 58, 70);

    i {
        font-size: 75px;
        color: rgb(30, 215, 96);
    }

    select {
        margin-right: 40px;
    }
}
</style>
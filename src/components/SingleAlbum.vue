@<template>
    <div>
        <img class="img-fluid" :src="poster" alt="">
        <h5>{{ title }}</h5>
        <h6>{{ author }}</h6>
        <h6>{{ year }}</h6>
        <h6>{{ genre }}</h6>
    </div>
</template>

<script>
export default {
    name: "SingleAlbum",
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
        genre: String
    }
}

</script>

<style lang="scss" scoped>
h5 {
    display: flex;
    justify-content: center;
    color: white;
    margin-top: 5px;
}

h6 {
    color: rgb(115, 119, 122);
}
</style>
@<template>
    <div class="bg-grey">
        <div class="container">
            <div class="row d-flex justify-content-center p-5">
                <div v-for="(album, i) in filteredAlbum" :key="i"
                    class="card col-lg-2 col-md-5 col-sm-10 m-3 text-center">
                    <SingleAlbum :poster="album.poster" :title="album.title" :author="album.author" :year="album.year"
                        :genre="album.genre" />
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import axios from "axios";
import SingleAlbum from "./SingleAlbum.vue";
export default {
    name: "MyMain",
    data() {
        return {
            albums: []
        };
    },
    mounted() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
            console.log(this.albums);
            this.albums = res.data.response;
        });
    },
    components: { SingleAlbum },
    props: {
        selectGenre: String
    },
    computed: {
        filteredAlbum() {
            if (this.selectGenre === "") {
                return this.albums
            }
            return this.albums.filter((album) => {
                if (album.genre === this.selectGenre) return true;


            })

        }
    }
}
</script>

<style lang="scss" scoped>
.bg-grey {
    background-color: rgb(30, 45, 59);
}

.card {
    min-height: 300px;
    padding: 25px;
    border-radius: 0;
    background-color: rgb(46, 58, 70);

}
</style>
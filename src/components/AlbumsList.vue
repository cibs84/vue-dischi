<template>
    <section class="albums-section">
        <div class="container">
            <div class="row row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5">
                <AlbumCard 
                    v-for="(singleAlbum, index) in dataAlbums" 
                    :key="index" 
                    :url="singleAlbum.poster"
                    :title="singleAlbum.title"
                    :author="singleAlbum.author"
                    :year="singleAlbum.year"
                />
            </div>
        </div>
    </section>
</template>


<script>
import AlbumCard from "./AlbumCard.vue";
import axios from "axios";

export default {
    name: 'AlbumsList',
    components: {
        AlbumCard
    },
    data(){
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            dataAlbums : [],
            transferCompleted: false
        }
    },
    methods: {
        getDataAlbums() {
            axios.get(this.url).then(response => {
                this.dataAlbums = response.data.response;
                this.transferCompleted = true;
            })
            .catch(err => {
                console.log("Error: ", err)
            });
        }
    },
    created() {
        this.getDataAlbums();
    }
}
</script>


<style lang="scss" scoped>
@import '../assets/styles/variables.scss';

.albums-section {
    background-color: $bg_secondary;
    padding: 5rem 0 4rem;
}
@media (min-width: 1400px){
    .container {
        max-width: 1100px;
    }
}
</style>
<template>
    <section class="albums-section" :class="{loader: !this.transferCompleted}">
        <div class="container">
            <!-- Le cards album saranno visualizzate SE sarà completato il trasferimento dei dati relativi agli album -->
            <div 
                class="row row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-5"
                v-if="this.transferCompleted"
            >
                <AlbumCard 
                    v-for="(singleAlbum, index) in dataAlbums" 
                    :key="index" 
                    :url="singleAlbum.poster"
                    :title="singleAlbum.title"
                    :author="singleAlbum.author"
                    :year="singleAlbum.year"
                />
            </div>

            <!-- ALTRIMENTI sarà visualizzato lo SpinneLoader fino al completamento del trasferimento dati -->
            <SpinnerLoader v-else/>
        </div>
    </section>
</template>


<script>
import AlbumCard from "./AlbumCard.vue";
import SpinnerLoader from "./SpinnerLoader.vue";
import axios from "axios";

export default {
    name: 'AlbumsList',
    components: {
        AlbumCard,
        SpinnerLoader
    },
    data(){
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            dataAlbums : [],
            transferCompleted: false,
        }
    },
    methods: {
        // Preleva i dati degli album con una chiamata all'endpoint contenuto nella variabile 'url'
        getDataAlbums() {
            axios.get(this.url).then(response => {
                // Ciò che restituisce il server chiamato, sarà memorizzato nell'array 'dataAlbums' precedentemente creato
                this.dataAlbums = response.data.response;
                // Per testare lo spinner loader è stato impostato un delay per rendere true la variabile di controllo del trasferimento completato
                setTimeout(() => {
                    this.transferCompleted = true;
                }, 2000);
            })
            .catch(err => {
                console.log("Error: ", err)
            });
        }
    },
    created() {
        // Prima della creazione del DOM invoco la funzione per prelevare i dati relativi agli album
        this.getDataAlbums();
    }
}   
</script>


<style lang="scss" scoped>
@import '../assets/styles/variables.scss';

.albums-section {
    background-color: $bg_secondary;
    padding: 5rem 0 4rem;

    .container {
        max-width: 1100px;
    }
}
.albums-section.loader {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
</style>
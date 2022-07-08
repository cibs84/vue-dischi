<template>
    <section class="albums-section">
        <div class="container">
            <div class="row row-cols-5">
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
                <AlbumCard :msg="miaVar"/>
            </div>
        </div>
    </section>
</template>


<script>
import AlbumCard from "./AlbumCard.vue";

export default {
    name: 'AlbumsList',
    components: {
        AlbumCard
    },
    data(){
        return {
            miaVar: "Hello!!"
        }
    }
}
</script>


<style lang="scss" scoped>
@import '../assets/styles/variables.scss';

.albums-section {
    background-color: $bg_secondary;
    padding: 3rem 0;
}
</style>
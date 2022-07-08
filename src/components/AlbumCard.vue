<template>
    <div class="col">
        <div class="album-card">
            <h2 class="text-uppercase">{{msg}}</h2>
        </div>
    </div>
</template>


<script>
export default {
    name: 'AlbumCard',
    props: {
        msg: String
    }
}
</script>


<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

.col {

    .album-card {
        background-color: $bg_primary;
        color: white;
    }
}
</style>
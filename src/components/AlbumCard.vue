<template>
    <div class="col">
        <div class="album-card">
            <img class="album-image" :src="url" :alt="`${author} - ${title}`">
            <h2 class="album-title">{{ title }}</h2>
            <div class="album-author">{{ author }}</div>
            <div class="album-year">{{ year }}</div>
        </div>
    </div>
</template>


<script>
export default {
    name: 'AlbumCard',
    props: {
        url: String,
        title: String,
        author: String,
        year: String
    }
}
</script>


<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

.col {
    
    .album-card {
        background-color: $bg_primary;
        color: white;
        text-align: center;
        padding: 1rem;
        padding-bottom: 0.5rem;
        height: calc(100% - 1rem);
        margin-bottom: 1rem;
        outline: 2px solid $bg_primary;
        transition: all 0.2s;
        cursor: pointer;

        .album-image {
            margin-bottom: 1rem;
        }
        .album-title {
            text-transform: uppercase;
            font-size: 0.8rem;
            font-weight: 600;
        }
        .album-author, 
        .album-year {
            color: #747c86;
            font-size: 0.7rem;
            font-weight: 600;
        }
    }
    .album-card:hover {
        outline: 2px solid #747c86;
    }
}
</style>
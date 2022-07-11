<template>
    <select 
        class="form-select mb-5"
        v-model="selectedGenre"
        @change="$emit('genreFilter', selectedGenre)"
    >
        <option :value="genre">{{genre}}</option>
        <option selected disabled>Visualizza album per genere musicale</option>
        <option value="all">Tutti i generi musicali</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</template>


<script>
export default {
    name: 'GenreFilter',
    data() {
        return {
            selectedGenre: 'all'
        }
    }
}
</script>


<style lang="scss" scoped>
@import '../assets/styles/variables.scss';

select {
    background-color: $bg_primary;
    color: white;
    border-color: gray;
}

</style>
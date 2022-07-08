<template>
    <header>
        <span class="spotify-icon">
            <i class="fa-brands fa-spotify"></i>
        </span>
    </header>
</template>


<script>
export default {
    name: 'MyHeader'
}
</script>


<style lang="scss" scoped>
@import "../assets/styles/variables.scss";

header {
    background-color: $bg_primary;
    
    .spotify-icon {
    color: #1dd65f;
    margin: 0.5rem 1rem;
    font-size: 2rem;
}
}
</style>
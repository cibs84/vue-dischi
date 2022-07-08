<!-- Descrizione: Create un nuovo progetto utilizzando Vue CLI e definite i componenti necessari per strutturare il layout come da screenshot allegato. Al caricamento della pagina, effettuate una chiama ajax all'API di boolean: https://flynn.boolean.careers/exercises/api/array/music e con i dati restituiti, stampate una card per ogni disco musicale.
Bonus: Creare un componente loader da visualizzare fintantoché i risultati non sono pronti. -->


<template>
  <div id="app">
    <MyHeader />

    <main>
      <AlbumsList />
    </main>
  </div>
</template>


<script>
import MyHeader from './components/MyHeader.vue';
import AlbumsList from './components/AlbumsList.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    AlbumsList
  }
}
</script>


<style lang="scss">
@import "./assets/styles/commons.scss";
@import "./assets/styles/variables.scss";
</style>

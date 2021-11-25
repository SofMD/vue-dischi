<template>
  <div id="app">

    <Header/>

    <main>
      <DischiList/>
    </main>

  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import DischiList from '@/components/DischiList.vue';

export default {
  name: 'App',
  components: {
    Header,
    DischiList,

  }
}
</script>

<style lang="scss">
 *{
   margin: 0;
   padding: 0;
   font-family: 'Roboto', sans-serif;
   box-sizing: border-box;
 }

</style>

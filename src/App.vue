<template>
  <div id="app">

    <Header @performClick=" searchgenre"/>

    <main>
      <DischiList :cd="dischi"/>
    </main>

  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import DischiList from '@/components/DischiList.vue';

export default {
  name: 'App',
  components: {
    Header,
    DischiList,

  },

  data(){
        return{
            dischi: null,
        };
    },
    created() {
        this.genDischi();
    },
    methods: {
        genDischi() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                console.log(result.data.response);
                this.dischi = result.data.response;
            })
            .catch(err => console.log(err));

        },

        searchgenre(text){
          console.log(text)
        }
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

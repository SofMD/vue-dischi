<template>
  <div id="app">

    <Header @performClick=" searchgenre"/>

    <main>
      <DischiList :cd="filteredgenre"/>
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
            selectedgen: 'All genres',
        };
    },
    computed: {
      filteredgenre() {
        if(this.selectedgen === 'All genres'){
          return this.dischi;
        }
        return this.dischi.filter(item => {
          return item.genre.toLowerCase().includes(this.selectedgen.toLowerCase())
        });
       
      //  return this.dischi.filter(item => {
        //    return item.genre.includes(this.selectedgen)
        //  });
      }

     
    },

    created() {
        this.genDischi();
    },
    methods: {
        genDischi() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                this.dischi = result.data.response;
            })
            .catch(err => console.log(err));

        },

        searchgenre(text){
          this.selectedgen = text;
          console.log(this.selectedgen);
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

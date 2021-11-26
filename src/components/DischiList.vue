<template>
  <section>
      <ul v-if="cd !== null" class="dischi-list">

          <li v-for="(el, i ) in cd" :key="`dischi-${i}`">
              <Cards 
                 :poster="el.poster"
                 :title="el.title"
                 :author="el.author"
                 :year="el.year"
                 :genre="el.genre"
              />

          </li>
      </ul>
      <div v-else>Loading...</div>
  </section>
</template>

<script>

import Cards from '@/components/Cards.vue'

export default {
    name: 'DischiList',
    components: {
        Cards,
    },
    props: {
        cd: Array
    },
    // data(){
    //     return{
    //         dischi: null,
    //     };
    // },
    // created() {
    //     this.genDischi();
    // },
    // methods: {
    //     genDischi() {

    //         axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    //         .then(result => {
    //             console.log(result.data.response);
    //             this.dischi = result.data.response;
    //         })
    //         .catch(err => console.log(err));

    //     },
    // }
}
</script>

<style scoped lang="scss">
section{
    width: 100%;
    background-color: #1d2d3c;


    ul{
        width: 95%;
        padding: 120px 0;
        margin: 0 auto;
        list-style: none;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        color: white;

        li{
            margin: 10px 17px;

        }
    }
}

</style>
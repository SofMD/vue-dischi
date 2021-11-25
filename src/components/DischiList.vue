<template>
  <section>
      <ul v-if="dischi !== null" class="dischi-list">

          <li v-for="(el, i ) in dischi" :key="`dischi-${i}`">

              <img :src="el.poster" :alt="el.title">
              <h2>{{el.title}}</h2>
              <div>
                  <h3>{{el.author}}</h3>
                  <div>{{el.year}}</div>
              </div>
              <div>{{el.genre}}</div>
              
          </li>
      </ul>
      <div v-else>Loading...</div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
    name: 'DischiList',
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
                console.log(result.data);
                this.dischi = result.data;
            })
            .catch(err => console.log(err));

        },
    }
}
</script>

<style scoped lang="scss">
section{
    width: 100%;
    height: 100vh;
    background-color: #1d2d3c;


    ul{
        width: 90%;
        padding: 120px 0;
        margin: 0 auto;
        list-style: none;
        display: flex;
        flex-wrap: wrap;
        color: white;

        li{
            margin-right: 30px;
        }
    }
}

</style>
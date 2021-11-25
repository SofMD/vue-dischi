<template>

<div class="card">
    <img :src="poster" :alt="title">
    <div class="text-cont">
        <h2>{{title}}</h2>
        <div class="text-light">
           <h3>{{author}}</h3>
           <div>{{year}}</div>
        </div>
        <div>{{genre}}</div>
    </div>
</div>
  
</template>

<script>
export default {
    name: 'Cards',
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
        genre: String,
    }
}
</script>

<style scoped lang="scss">

.card{
    height: 100%;
    background-color: #2e3a46;
    padding: 15px 20px;

    img {
        width: 150px;
        height: 150px;
        object-fit: cover;
    }

    .text-cont{
        width: 150px;
        height: 100%;
        text-align: center;

        h2 {
            margin: 20px 0;
            font-size: 1.3rem;
            text-transform: uppercase;
        }

        .text-light{
            color: #7f7f7d;
            margin-bottom: 10px;
        }
    }
}

</style>
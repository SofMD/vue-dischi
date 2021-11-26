<template>

<header >
    <img src="../assets/logosp.png" alt="">

    <div class="sel-cont">
        <div class="head-text">SCEGLI IL GENERE CHE PREFERISCI:</div>
        <select name="genereCd" id="genereCd" v-model="nameInput">
            <option @click="$emit('performClick', nameInput)" value="All genres">All genres</option>
            <option @click="$emit('performClick', nameInput)" value="rock">Rock</option>
            <option @click="$emit('performClick', nameInput)" value="pop">Pop</option>
            <option @click="$emit('performClick', nameInput)" value="jazz">Jazz</option>
            <option @click="$emit('performClick', nameInput)" value="metal">Metal</option>
        </select>
    </div>

    
</header>
</template>

<script>
export default {
    name: 'Header',

    data(){
        return {
            nameInput: 'All genres',
        }
    }
}
</script>

<style scoped lang="scss">

header{
    background-color: #2e3a46;
    padding: 5px;
    display: flex;
    align-items: center;
    justify-content: space-between;

    img{
        width: 50px;
    }

    .sel-cont{
        display: flex;
        align-items: center;
        margin: 30px;
    }

    .head-text{
        font-size: 15px;
        color: white;
    }

    #genereCd{
        margin: 0 10px;
        color: black;
        background-color: white;
        border: none;
        padding: 10px 20px;
    }
}

</style>
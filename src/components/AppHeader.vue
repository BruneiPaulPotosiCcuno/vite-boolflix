
<script>
import { store } from '../store.js';
export default {
    name: 'AppHeader',
    data() {
        return {
            store
        };
    },
}
</script>

<template>
    <header class="container">
        <h1>BOOLFLIX</h1>
        <div class="nav-search">
            <input type="text" class="imput-css" v-model="store.searchText">
            <button @click="$emit('searchUser')" href="" class="original-button">Cerca</button>
        </div>

    </header>
    

</template>

<style scoped lang="scss">

    .container{
        display: flex;
        justify-content: space-around;
        align-items: center;
        
        .imput-css{
        height: 20px;
        padding: 4px;
        font-size: 16px;
        background-color: #FFFFFF;
        color: #000000;
        border-style: solid;
        border-radius: 0px;
        box-shadow: 1px 0px 7px rgba(220,41,41,.73);
        text-shadow: -50px 0px 0px rgba(66,66,66,.75);
        }

        
    }

    header{
        
        font-size: 20px;
        background-color: rgb(0, 0, 0);
        height: 80px;

        
        
        h1{
            
            align-items: center;
            position: relative;
            left: 90px;
            color: #f34144;
            font-weight: 600;
        }


    }

    .original-button {
  justify-content: center;
  line-height: 1;
  text-decoration: none;
  font-size: 15px;
  border-radius: 0px;
  width: 200px;
  height: 40px;
  border: 2px solid #333333;
  transition: 0.3s;
  background-color: #ffffff;
}

.original-button:hover {
  box-shadow: 0 0 #333;
  color: #fff;
  background-color: #333;
}
</style>
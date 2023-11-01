<script setup>
import { ref } from 'vue';

  let qty = ref(27)
  function addvalue(){
    qty.value++
  }
  function reducevalue(){
    if(qty.value > 0){
      qty.value--
    }
  }
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="ballon" v-show="qty > 0">{{ qty }}</div>
    </div>

    <div class="button-wrapper">
      <div class="button" @click="reducevalue">
        -
      </div>
      <div class="button" @click="addvalue">
        +
      </div>
      <div v-if="qty>0">Me escribieron</div>
      <div v-else>Nadie me escribe 😒</div>
    </div>
  </div>
</template>

<style scoped>
  .button{
    background-color: #DAFDBA;
    display: inline-block;
    padding: 4px 0;
    border-radius: 4px;
    width: 32px;
    margin: 0 10px;
  }
  .button:hover{
    cursor: pointer;
    background-color: #BFB78F;
  }

  .button-wrapper{
    margin-bottom: 16px;
    text-align: center;
    margin-top: 16px;
  }
  .ballon{
    position: absolute;
    top: 0;
    right: 0;
    width: 32px;
    height: 32px;
    background-color: #D92525;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
  }
  .profile{
    background-image: url('https://shiftart.com/wp-content/uploads/2017/04/RC-Profile-Square.jpg') ;
    background-size: cover;
    position: relative;
    background-color: brown;
    width: 160px;
    height: 160px;
    margin: 0 auto;
    border-radius: 100%;
  }
  .wrapper {
    overflow: hidden;
    padding-top: 18px;
    background-color: #6B0070;
    width: 60%;
    border-radius: 12px;
    margin: 0 auto;
  }
</style>

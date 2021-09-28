<template>
  <div id="app">

    <header>
      <img alt="Vue logo" src="./assets/logo.png">

      <p>User</p>
      <p>Login</p>
      <p>connexion</p>
    </header>
    <BaseLayout>
      <HomePage/>
      <BaseButton :colorPalette="colorPalette"/>
      <AsyncButton/>
    </BaseLayout>

  </div>
</template>

<script>
import HomePage from "@/components/HomePage";
import BaseLayout from "@/components/BaseLayout";
import BaseButton from "@/components/BaseButton";
import AsyncButton from "@/components/AsyncButton";

export default {
  name: 'App',
  components: {
    HomePage,
    BaseLayout,
    BaseButton,
    AsyncButton
  },
  data(){
    return{
      colorPalette : {
        primary: {bg: '#42b983', hoverBg: '#4cce93', focusBorder: '#47d696'},
        warn: {bg: '#ff5722', hoverBg: '#ff7043', focusBorder: '#ff8a65'},
        danger: {bg: '#e53935', hoverBg: '#ef5350', focusBorder: '#e57373'},
      },
    }
  },
  methods : function (){

  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


header{
  display: flex;
  justify-content: space-evenly;
  color: midnightblue;
  background: #3CB371;
  max-height: 250px;
}
</style>

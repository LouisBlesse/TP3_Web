<template>
  <div id="app">
    <header>
      <img alt="Vue logo" src="./assets/logo.png" />
      <p>User</p>
      <p>Login</p>
      <p>connexion</p>
    </header>
    <HomePage />

    <BaseLayout>
      <BaseButton color="primary">primary</BaseButton>
      <br />
      <BaseButton color="danger">danger</BaseButton>
      <br />
      <BaseButton color="warn">warn</BaseButton>
      <br />
      <BaseButton color="danger" disabled>danger disabled</BaseButton>
    </BaseLayout>
  </div>
</template>

<script>
import HomePage from "@/components/HomePage";
import BaseLayout from "@/components/BaseLayout";
import BaseButton from "@/components/BaseButton";

export default {
  name: "App",
  components: {
    HomePage,
    BaseLayout,
    BaseButton,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  display: flex;
  justify-content: space-evenly;
  color: midnightblue;
  background: #3cb371;
  max-height: 250px;
}
</style>

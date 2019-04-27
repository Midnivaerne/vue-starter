<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="isLogged == false">
      <div>Zaloguj się e-mailem:
        <input type="email" v-model="email">
        <button @click="logIn()">Zaloguj</button>
      </div>
    </div>
    <div v-else-if="isLogged == true">
      <h2>Witaj, {{email}}!</h2>
      <div @click="logOff()"><u>Wyloguj</u></div>

    </div>
  </div>
</template>

<script>
export default {

    data() {
        return {
            isLogged: false,
            email: 'e@mail.com',
            password: ''
        };

    },
    methods: {
        alertMyEmail() {
            alert(this.email);
        },
        logOff(){
            this.isLogged=false;
            this.email= '';
        },
        logIn(){
            this.isLogged=true;
        }
    }
  }

</script>

<style>
</style>

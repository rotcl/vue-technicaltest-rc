<template>
  <section class="is-large">
    <button class="button is-outlined" @click="getAxios()">Conseguir usuario</button>
    <div v-if="nombre != ''" class="notification is-warning">
        <div class="has-text-centered">
          <img v-bind:src="foto" alt="">
          <h3 class="name title is-3"> {{ nombre }} </h3>
          <p class="mail">{{ mail }}</p>
          <p class="direccion">{{ direccion }}</p>
        </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      nombre: '',
      mail: '',
      foto: ''
    };
  },
  methods: {
    getAxios: function(){
      axios
        .get('https://randomuser.me/api/')
        .then(response => {
          const rsp = response.data.results[0];
          this.nombre = rsp.name.first + ' ' + rsp.name.last;
          this.mail = rsp.email;
          this.foto = rsp.picture.large;
          this.direccion = rsp.location.street + ' ' + rsp.location.city + ' ' + rsp.location.state
          })
    }
  }
};
</script>

<style scoped>
.button{
    margin-bottom: 2em;
  }
.user span{
    margin-bottom: 1em;
  }
.name, .direccion{
    text-transform: capitalize;
  }
</style>

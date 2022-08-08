<template>
  <div>
    <h1 :class="titleCss">
      {{ title }}
    </h1>
    <BaseAlert
      variant="success"
      @close="onClose()"
    >
      Enviado com sucesso
    </BaseAlert>
    <p class="card">ads</p>
    <BaseCard>
    </BaseCard>
    <TheHeader v-if="visible">
      <template v-slot:title>
        titulo
      </template>
      Content do TheHeader
    </TheHeader>
    
    <div @="show">
      v-show
    </div>
    <div v-if="user === 'admin'">Usuário Admin</div>
    <div v-else-if="user === 'marketing'">Usuário Marketing</div>
    <div v-else>Usuário comun</div>
    <div>
      <div class="obj" v-for="(obj, index) in list" :key="index">
        <img v-if="obj.imgSrc" :src="obj.imgSrc" />
        {{ obj.title }}
      </div>
    </div>

    <div>
      <div class="next">
        <label>Nome</label><br>
        <input v-model="name" type="text" /><br>
        {{ name }}
      </div>
      <div class="next">
        <label>Sexo</label><br>
        <input v-model="sexo" type="radio" value="masc" /> Masculino<br>
        <input v-model="sexo" type="radio" value="fem" /> Feminino<br>
        {{ sexo }}
      </div>
      <div class="next">
        <label>Contrato</label><br>
        <input v-model="contract" type="checkbox" value="aceite" /> Aceita os termos<br>
        <input v-model="contract" type="checkbox" value="aceite_email" /> Aceita receber emails<br>
        {{ contract }}
      </div>
      <div class="next">
        <label>Alert</label><br>
        <button :class="btn" @click="onClick">Danger</button>
      </div>
    </div>
    <div>
      <input v-model="name1" type="text" /><br>
      {{ name1 }}
    </div>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BaseCard from "@/components/BaseCard.vue";
import BaseAlert from "./components/BaseAlert.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    BaseCard,
    BaseAlert
},
  data() {
    return {
      name1: '',
      btn: ['btn_danger'],
      contract: [],
      sexo: '',
      name: 'two way data binding',
      title: 'Curso dominando o Vue',
      titleCss: ['title', { 'home': true }],
      visible: true,
      show: true,
      user: "marketing",
      list: [
        {
          "userId": 1,
          "id": 1,
          "title": "delectus aut autem",
          "completed": false,
          "imgSrc": 'http://via.placeholder.com/60x60'
        },
        {
          "userId": 1,
          "id": 2,
          "title": "quis ut nam facilis et officia qui",
          "completed": false,
          "imgSrc": 'http://via.placeholder.com/60x60'
        },
        {
          "userId": 1,
          "id": 3,
          "title": "fugiat veniam minus",
          "completed": false,
          "imgSrc": ''
        },
        {
          "userId": 1,
          "id": 4,
          "title": "et porro tempora",
          "completed": true
        },
        {
          "userId": 1,
          "id": 5,
          "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
          "completed": false
        },
      ]
    }
  },

  watch: {
    name1(newValue, oldValue) {
      this.returnValuesName(newValue, oldValue);
    }
  },

  methods: {
    onClick() {
      alert('Perigooooooo, o Vue é lindo! :) ;)');
    },
    returnValuesName(newValue, oldValue) {
      console.log(newValue, oldValue);
    },
    onClose() {
      console.log('close')
    }
  },
};
</script>

<style>
.btn_danger {
  background-color: red;
  color: #fff;
  border-radius: 5px;
  padding: 10px;
}
.next {
  margin-top: 30px;
}
.title {
  color: red;
  font-size: 5rem;
}
.home {
  background-color: #000;
}
.obj {
  margin-top: 10px;
  padding: 5px;
  border-radius: 5px;
  background-color: #000;
  color: #fff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px;
}
</style>

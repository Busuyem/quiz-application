<script setup>
import q from './assets/data/quizes.json'
import {ref, watch} from "vue"
import Card from './components/Card.vue'

const quizes = ref(q)
const search = ref("")

watch(search, ()=>{
  quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})

</script>

<template>
  <div class="container">
      <header>
        <h1>Quizes</h1>
        <input v-model.trim="search" type="text" placeholder="Search...">
      </header>

      <div class="container-options">
        <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>>
        <!--
        <div class="card" v-for="quiz in quizes" :key="quiz.id">
          <img :src="quiz.image" alt="No Image">
          <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length }}</p>
          </div>
        </div>
        -->
      </div>
  </div>
</template>

<style>
    .container{
      max-width: 1000px;
      margin: 0 auto;
      margin-bottom: 10px;
      margin-top: 30px;
    }

    header{
      display: flex;
      align-items: center;
    }

    header h1{
      font-weight: bold;
      margin-right: 30px;
    }

    header input{
      border-radius: 5px;
      border: 0px;
      background-color: rgba(130, 120, 110, 0.1);
      padding:10px;
    }

    .container-options{
      display: flex;
      flex-wrap: wrap;
      padding: 10px;
    }

    /*
    .card{
      width: 310px;
      overflow: hidden;
      border-radius: 2px;
      box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
      margin-bottom: 35px;
      margin-right: 20px;
      margin-top: 30px;
      cursor: pointer;
    }
    

    .card img{
      width: 100%;
      height: 150px;
      margin: 0;
    }

    .card .card-text{
      padding: 15px;

    }

    .card h2{
      font-weight: bold;
    }

    */
</style>
<script setup>
import {defineProps} from 'vue'
import { useRouter } from 'vue-router';

const {quiz} = defineProps(['quiz'])

const router = useRouter()

const navigateThroughQuiz = () =>{
    router.push(`quizes/${quiz.id}`)
}

//console.log('quiz')

</script>

<template>
    <div>
        <div class="card" @click="navigateThroughQuiz">
            <img :src="quiz.image" alt="No Image">
            <div class="card-text">
              <h2>{{ quiz.name }}</h2>
              <p>{{ quiz.questions.length }} questions</p>
            </div>
          </div>
    </div>
</template>

<style>

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

</style>
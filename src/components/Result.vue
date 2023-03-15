<script setup>
import { defineProps } from 'vue';
import { RouterLink } from 'vue-router';

const {numOfCorrectAnswer, totalQuestions} = defineProps(['numOfCorrectAnswer', 'totalQuestions'])

</script>

<template>
    <div class="result">

        <p>Your result...</p>

        <h2>
            {{numOfCorrectAnswer }}/{{ totalQuestions }}
        </h2>

        <RouterLink to="/">Go Back</RouterLink>
    </div>
</template>

<style scoped>
    .result{
        text-align: center;
        padding: 100px 0;
    }

    p{
        font-size: 20px;
    }

    h2{
        font-size: 80px;
    }
</style>
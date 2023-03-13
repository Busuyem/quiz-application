<script setup>
    import Question from '../components/Question.vue';
    import QuizHeader from '../components/QuizHeader.vue'
    import {useRoute} from 'vue-router'
    import { ref, watch, computed } from 'vue';
    import quizes from '../assets/data/quizes.json'

    const router = useRoute()

    const quizId = parseInt(router.params.id)

    const currentQuestionIndex = ref(0)

    const quiz = quizes.find(q => q.id === quizId)

    //Alternatively
    // const questionStatus = ref(`${currentQuestionIndex.value}/${quiz.questions.length}`)

    // watch(()=> currentQuestionIndex.value, () => {
    //     questionStatus.value = `${currentQuestionIndex.value}/${quiz.questions.length}`
    // })

    const questionStatus = computed(()=> {
       return `${currentQuestionIndex.value}/${quiz.questions.length}`
    })

    const barPercentage = computed(()=> `${currentQuestionIndex.value/quiz.questions.length *100}%`)
</script>

<template>
    <div>
        <QuizHeader :questionStatus="questionStatus" :barPercentage="barPercentage"/>
        <Question :question="quiz.questions[currentQuestionIndex]" />
        <button @click="currentQuestionIndex++">Next Question</button>
        <button @click="currentQuestionIndex--">Back</button>
    </div>
</template>

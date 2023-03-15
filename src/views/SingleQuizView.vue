<script setup>
    import Question from '../components/Question.vue';
    import QuizHeader from '../components/QuizHeader.vue'
    import {useRoute} from 'vue-router'
    import { ref, watch, computed } from 'vue';
    import quizes from '../assets/data/quizes.json'
    import Result from '../components/Result.vue'

    const router = useRoute()

    const quizId = parseInt(router.params.id)

    const currentQuestionIndex = ref(0)

    const quiz = quizes.find(q => q.id === quizId)

    const numOfCorrectAnswer = ref(0)
    const showResult = ref(false)

    //Alternatively
    // const questionStatus = ref(`${currentQuestionIndex.value}/${quiz.questions.length}`)

    // watch(()=> currentQuestionIndex.value, () => {
    //     questionStatus.value = `${currentQuestionIndex.value}/${quiz.questions.length}`
    // })

    const questionStatus = computed(()=> {
       return `${currentQuestionIndex.value}/${quiz.questions.length}`
    })

    const barPercentage = computed(()=> `${currentQuestionIndex.value/quiz.questions.length *100}%`)

    const onOptionSelect = (isCorrect)=>{
        if(isCorrect){
            numOfCorrectAnswer.value++
        }

        if(quiz.questions.length -1 === currentQuestionIndex.value){
            showResult.value = true
        }

        currentQuestionIndex.value++
    }


</script>

<template>
    <div>
        <QuizHeader :questionStatus="questionStatus" :barPercentage="barPercentage"/>
        <Question :question="quiz.questions[currentQuestionIndex]" 
        @selectOption="onOptionSelect" 
        v-if="!showResult"
        />
        <Result v-else 
        :numOfCorrectAnswer="numOfCorrectAnswer"
         :totalQuestions="quiz.questions.length"/>
    </div>

    
</template>

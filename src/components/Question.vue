<script setup>
    import { defineProps } from 'vue';

    const {question} = defineProps(['question'])


</script>

<template>
    <div class="question-container">
        <h3 class="question">
            {{ question.text }}
        </h3>
    </div>
    <div class="options-container">
        <div class="option" v-for="option in question.options" :key="option.id">
            <p class="option-label">{{ option.label }}</p>
            <div class="option-value">
                <p>{{ option.text }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>

.question-container{
    margin-top: 20px;
    margin-left: 20px;

}

.question{
    margin-top: 40px;
    margin-bottom: 20px;
    font-size: 40px;
    
}

.option{
    display: flex;
    margin-bottom: 20px;
    margin-left: 20px;
    cursor: pointer;
    
}

.option-label{
    background-color: bisque;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50px;
    width: 50px;
    font-size: 30px;
}

.option-value{
    background-color: rgba(250, 249, 249, 1);
    width: 100%;
    font-size: 30px;
    padding: 0 20px;

}

</style>
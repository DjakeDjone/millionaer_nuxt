<script lang="ts" setup>

const props = defineProps({
    question: String,
    answers: Array,
    correctAnswer: Number,
    idx: Number,
    question_length: Number
})

const emit = defineEmits(['answer'])
const handleAnswerClick = (answer: String) => {
    emit('answer', answer);
}
onMounted(() => {
    const audio = new Audio('/QuestionMusic.wav');
    // audio
    audio.play();
})
</script>

<template>
    <div class="container">
        <h2 class="question">{{ question }}</h2>
        <div class="answers">
            <button class="answer" v-for="answer, i in answers" :key="answer" @click="handleAnswerClick(answer)" :style="'animation-delay: ' + ((answers.length-i) * 0.3) + 's'">
                <span class="ans_number">
                    {{ String.fromCharCode(65 + i) }}: 
                </span>
                <span>
                    {{ answer }}
                </span>
            </button>
        </div>
    </div>
</template>

<style setup>
/* animate range slider  */

.ans_number {
    padding-right: 0.5rem;
}

#btmslider {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #eee;
    padding: 0.5rem;
    font-size: 0.8rem;
    text-align: center;
    color: black;
    opacity: 0.5;
}
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
    max-width: 40rem;
    margin: 0 auto;
    /* background: radial-gradient(#eee, #aaa); */
    /* background-image: url('/MillionärLogo.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat; */
}

.question {
    font-size: 2rem;
    margin-bottom: 2rem;
}

.answers {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 1rem;
    width: 100%;
}
.answer {
    font-size: 1.5rem;
    padding: 1rem;
    border: 1px solid black;
    border-radius: 0.5rem;
    background-color: white;
    display: flex;
    /* justify-content: space-between; */
    cursor: pointer;
    opacity: 0;
    animation: 0.5s ease-out 0s 1 slideInFromLeft forwards;
}
.answer > span {
    color: black;
}
.answer:hover {
    background-color: #eee;
}
.answer:active {
    background-color: #ddd;
}

@keyframes slideInFromLeft {
    0% {
        transform: translateX(-100%);
        opacity: 0;
    }
    100% {
        transform: translateX(0);
        opacity: 1;
    }
}
</style>
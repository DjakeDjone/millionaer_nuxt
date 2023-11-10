<script lang="ts" setup>

const props = defineProps({
    question: String,
    answers: Array,
    correctAnswer: Number,
})

const emit = defineEmits(['answer'])
const handleAnswerClick = (answer: String) => {
    emit('answer', answer);
}
onMounted(() => {
    const audio = new Audio('/Start_sound.mp3');
    // audio
    audio.play();
})
</script>

<template>
    <div class="container">
        <h2 class="question">{{ question }}</h2>
        <div class="answers">
            <button class="answer" v-for="answer in answers" :key="answer" @click="handleAnswerClick(answer)">
                {{ answer }}
            </button>
        </div>
    </div>
</template>

<style setup>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
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
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}
.answer {
    font-size: 1.5rem;
    margin: 0.5rem;
    padding: 0.5rem 1rem;
    border: 1px solid black;
    border-radius: 0.5rem;
    background-color: white;
    color: black;
    cursor: pointer;
}
.answer:hover {
    background-color: #eee;
}
.answer:active {
    background-color: #ddd;
}
</style>
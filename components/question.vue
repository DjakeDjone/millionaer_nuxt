<script lang="ts" setup>

const props = defineProps({
    question: String,
    answers: Array,
    correctAnswer: Number,
    idx: Number,
    question_length: Number
})

const emit = defineEmits(['answer'])
const clicked = ref(-1);
const handleAnswerClick = (answer: String) => {
    if (clicked.value !== -1) return;
    clicked.value = props.answers.indexOf(answer);
    if (clicked.value === props.correctAnswer) {
        const audio = new Audio('/Winsound.mp3');
        audio.play();
    } else {
        const audio = new Audio('/wah-wah-sound-effect.mp3');
        audio.play();
    }
    setTimeout(() => {
        clicked.value = -1;
        emit('answer', answer);
    }, 2000);
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
            <div class="answer" v-for="answer, i in answers" :key="answer" @click="handleAnswerClick(answer)"
                :style="'animation-delay: ' + ((answers.length - i) * 0.1) + 's'"
                :class="{ 'correct': (i === clicked && i == correctAnswer), 'wrong': (i === clicked && i != correctAnswer) }">
                <button>
                    <span class="ans_number">
                        {{ String.fromCharCode(65 + i) }}:
                    </span>
                    <span>
                        {{ answer }}
                    </span>
                </button>
            </div>
        </div>
    </div>
</template>

<style setup>
/* animate range slider  */
.correct>button {
    background-color: #00ff00 !important;
}

.wrong>button {
    background-color: #ff0000 !important;
}

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
    cursor: pointer;
    font-size: 1.5rem;
    border-radius: 0.5rem;
    background: linear-gradient(90deg,
            rgb(255, 0, 0) 0%,
            rgb(17, 255, 0) 50%,
            rgb(0, 119, 255) 100%);
    display: flex;
    /* justify-content: space-between; */
    padding: 0.2rem;
    cursor: pointer;
    opacity: 0;
    animation: 0.5s ease-out 0s 1 slideInFromLeft forwards;
}

.answer>button>span {
    color: black;
    display: inline-block;
}

.answer:hover {
    background-color: #eee;
}

.answer:active {
    background-color: #ddd;
}

button {
    cursor: pointer;
    color: black;
    background: white !important;
    padding: .5rem;
    border-radius: 0.5rem;
    width: 100%;
    height: 100%;
    border: none;
    background-color: transparent;
    font-size: 1.5rem;
    display: flex;
    justify-content: left;
    align-items: center;
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
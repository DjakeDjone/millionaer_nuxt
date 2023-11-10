<script lang="ts" setup>

export type Question = {
  question: string,
  answers: string[],
  correctAnswer: number
}

const questions: Question[] = [
  {
    question: 'Was ist die Hauptstadt von Frankreich?',
    answers: ['London', 'Rom', 'Paris', 'Madrid'],
    correctAnswer: 2,
  },
  {
    question: 'Was ist die Hauptstadt von Spanien?',
    answers: ['London', 'Rom', 'Paris', 'Madrid'],
    correctAnswer: 3,
  },
]

let idx = 0;
let currentQuestion = ref(questions[idx]);
let score = 0;
let status = ref('loading');

const handleAnswer = (answer: string) => {
  if (answer === currentQuestion.value.answers[currentQuestion.value.correctAnswer]) {
    score++;
  } else {
    status.value = 'lost';
    return;
  }
  idx++;
  if (idx < questions.length) {
    currentQuestion.value = questions[idx];
  } else {
    status.value = 'won';
    // alert(`Game over! Your score is ${score}`);
  }
}
onMounted(() => {
  const audio = new Audio('/Start_sound.mp3');
  audio.play();
  setTimeout(() => {
    status.value = 'playing';
    audio.pause();
  }, 2000);
})
</script>

<template>
  <main class="main">
    <div id="logo" :class="{ 'animate-spin': status === 'loading' }">
    </div>
    <div v-if="status == 'playing' && currentQuestion">
      <Question :question="currentQuestion.question" :answers="currentQuestion.answers"
        :correctAnswer="currentQuestion.correctAnswer" @answer="handleAnswer" />
    </div>
    <div v-if="status == 'won'">
      <Winner />
    </div>
    <div v-if="status == 'lost'">
      <Lost :score="score" />
    </div>
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #ffffff;
}

body {
  font-family: sans-serif;
}

</style><style scoped>.main {
  height: 100vh;
  background-color: #000000;
  background-image: url('/Bg.jpg');
  background-size: cover;
  background-position: center;
}



#logo {
  margin: 0 auto;
  width: 10rem;
  height: 10rem;
  background-image: url('/MillionärLogo.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  animation: spin 10s linear infinite, start_animation 2s ease-in-out;
}

.animate-spin {
  animation: spin 3s linear ease-in-out;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

@keyframes start_animation {
  0% {
    scale: 4;
  }

  100% {
    scale: 1;
  }
}</style>
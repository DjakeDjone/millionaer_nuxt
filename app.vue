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
    question: 'Wer entdeckte im Jahr 1492 Amerika?',
    answers: ['Christoph Columbus', 'Napoleon Bonaparte', 'Magellan', 'Elon Musk'],
    correctAnswer: 0,
  },
  {
    question: 'Welche Antwortmöglichkeit ist kein Kontinent?',
    answers: ['Europa', 'Asien', 'Arktis', 'Australien'],
    correctAnswer: 2,
  },
  {
    question: 'Wann begann der 2. Weltkrieg?',
    answers: ['1995', '1845', '1914', '1939'],
    correctAnswer: 3,
  },
  {
    question: 'Wie heißt der höchste Berg Österreichs?',
    answers: ['Schneeberg', 'Großglockner', 'Mount Everest', 'Mont Blanc'],
    correctAnswer: 1,
  },
  {
    question: 'Wer übersetzte in der Wartburg die Bibel ins Deutsche?',
    answers: ['Martin Luther King', 'Johannes Kepler', 'Johann Wolfgang von Goethe', 'Martin Luther'],
    correctAnswer: 3,
  },
  {
    question: 'Welches Nachbarland ist nicht teil der EU?',
    answers: ['Schweiz', 'Ungarn', 'Italien', 'Tschechische Rupublik'],
    correctAnswer: 0,
  },
  {
    question: 'Welche Adelsfamilie regierte fast 650 Jahre Österreich?',
    answers: ['Habsburger', 'Babenberger', 'die Gallier', 'Wittelsbacher'],
    correctAnswer: 0,
  },
  {
    question: 'Über welches Land in Afrika erstreckt sich die Sahara NICHT?',
    answers: ['Ägypten', 'Algerien', 'Marokko', 'Südafrika'],
    correctAnswer: 3,
  },
  {
    question: 'Wer ist bekannt für den Ausspruch Österreich ist frei?',
    answers: ['Alexander Van der Bellen', 'Kaiser Fanz Joseph', 'Karl Renner', 'Leopold Figel'],
    correctAnswer: 2,
  }
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
// watch change idx
onMounted(() => {
  const audio = new Audio('/Start_sound.mp3');
  audio.play();
  setTimeout(() => {
    status.value = 'playing';
    audio.pause();
  }, 8000);
})
</script>

<template>
  <main class="main">
    <div id="logo" :class="{ 'animate-spin': status === 'loading' }">
    </div>
    <div v-if="status == 'playing' && currentQuestion">
      <Question :idx="idx" :question="currentQuestion.question" :answers="currentQuestion.answers" :question_length="questions.length"
        :correctAnswer="currentQuestion.correctAnswer" @answer="handleAnswer" />
        <div id="btmslider">
            <!-- volume slider -->
            <input type="range" min="0" :max="questions.length" class="slider" id="myRange" v-model="idx">
        </div>
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

</style><style scoped>
#btmslider {
  width: 100%;
}
.slider {
    -webkit-appearance: none;
    width: 100% !important;
    height: 10px;
    border-radius: 5px;
    background: #ffffff;
    outline: none;
    opacity: 1;
    /* green slider icon  */
    -webkit-transition: .2s;
    transition: opacity .2s;
}

.slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 25px;
    height: 25px;
    border-radius: 50%;
    background: #4CAF50;
    cursor: pointer;
}

.slider::-moz-range-thumb {
    width: 25px;
    height: 25px;
    border-radius: 0;
    background: #4CAF50;
}


.main {
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
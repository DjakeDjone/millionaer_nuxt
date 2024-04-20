<script lang="ts" setup>

export type Question = {
  question: string,
  answers: string[],
  correctAnswer: number,
  difficulty: number, // 0 - 10
}



const questions_container: Question[] = [
  {
    "question": "Was ist das Minimalprinzip in der Wirtschaft?",
    "answers": [
      "Mit bestimmten Mitteln ein möglichst hohes Ziel erreichen.",
      "Die Produktion von Gütern mit unbegrenzten Ressourcen.",
      "Ein bestimmtes Ziel mit so möglichst geringem Mitteleinsatz erreichen."
    ],
    "correctAnswer": 2,
    "difficulty": 5
  },
  {
    "question": "Was charakterisiert Grund- und Existenzbedürfnisse?",
    "answers": [
      "Die Abdeckung dieser Bedürfnisse erhöht den Lebensstandard.",
      "Die Abdeckung dieser Bedürfnisse ist lebensnotwendig.",
      "Diese Bedürfnisse sind Luxusbedürfnisse."
    ],
    "correctAnswer": 1,
    "difficulty": 4
  },
  {
    "question": "Was umfasst die Volkswirtschaftliche Gesamtrechnung (VGR)?",
    "answers": [
      "Die Berechnung des Brutto Inlands Produkts (BIP).",
      "Die Analyse des Verhaltens von Unternehmen.",
      "Die Untersuchung und Darstellung des Wirtschaftsgeschehens einer Volkswirtschaft für eine abgelaufene Periode."
    ],
    "correctAnswer": 0,
    "difficulty": 7
  },
  {
    "question": "Was bedeutet das 1. Gossen'sche Gesetz?",
    "answers": [
      "Der Nutzen eines Gutes nimmt mit zunehmender Bedürfnisbefriedigung ab.",
      "Je größer der Grenznutzen eines Produktes ist, desto mehr ist ein Konsument bereit zu zahlen.",
      "Der Nutzen steigt, wenn mehr von einem Gut konsumiert wird."
    ],
    "correctAnswer": 0,
    "difficulty": 6
  },
  {
    "question": "Was sind Wirtschaftsgüter?",
    "answers": [
      "Güter, die einen Preis haben, müssen produziert und bezahlt werden.",
      "Güter, die scheinbar unbegrenzt vorhanden sind.",
      "Güter, die durch den Staat reguliert werden."
    ],
    "correctAnswer": 0,
    "difficulty": 5
  },
  {
    "question": "Was ist der Zweck von Banken im Wirtschaftskreislauf?",
    "answers": [
      "Geldanlagen entgegennehmen und Kredite vergeben.",
      "Produktion von Gütern und Dienstleistungen.",
      "Den Gleichgewichtspreis auf dem Markt festlegen."
    ],
    "correctAnswer": 0,
    "difficulty": 6
  },
  {
    "question": "Was sind freie Güter?",
    "answers": [
      "Güter, die durch Kaufkraft befriedigt werden können.",
      "Güter, die scheinbar unbegrenzt vorhanden sind.",
      "Güter, die einen Preis haben und produziert werden müssen."
    ],
    "correctAnswer": 1,
    "difficulty": 4
  },
  {
    "question": "Was umfasst die Mikroökonomie?",
    "answers": [
      "Die Untersuchung gesamtwirtschaftlicher Phänomene.",
      "Die Analyse des Verhaltens von einzelnen Wirtschaftsteilnehmern.",
      "Die Produktion von Gütern und Dienstleistungen."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was beschreibt die Marktform?",
    "answers": [
      "Die Anzahl der Anbieter und Nachfrager auf dem Markt.",
      "Den Preiselastizität der Nachfrage.",
      "Die Höhe des Brutto Inlands Produkts (BIP)."
    ],
    "correctAnswer": 0,
    "difficulty": 6
  },
  {
    "question": "Was sind Kultur- und Sozialbedürfnisse?",
    "answers": [
      "Die Abdeckung dieser Bedürfnisse ist lebensnotwendig.",
      "Die Abdeckung dieser Bedürfnisse erhöht den Lebensstandard.",
      "Diese Bedürfnisse sind Luxusbedürfnisse."
    ],
    "correctAnswer": 1,
    "difficulty": 4
  },
  {
    "question": "Was versteht man unter dem Maximalprinzip?",
    "answers": [
      "Mit bestimmten Mitteln ein möglichst hohes Ziel erreichen.",
      "Ein bestimmtes Ziel mit so möglichst geringem Mitteleinsatz erreichen.",
      "Die Produktion von Gütern mit unbegrenzten Ressourcen."
    ],
    "correctAnswer": 0,
    "difficulty": 7
  },
  {
    "question": "Was sind öffentliche Unternehmen?",
    "answers": [
      "Unternehmen, die sich im Besitz von Privatpersonen befinden.",
      "Unternehmen, die staatlich sind (z.B. ÖBB, ORF).",
      "Unternehmen, die gemeinnützige Dienstleistungen anbieten."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was ist der Staat im Wirtschaftskreislauf?",
    "answers": [
      "Ein Wirtschaftsteilnehmer, der Geldanlagen entgegennimmt.",
      "Ein Wirtschaftsteilnehmer, der mit Gesetzen regulierend eingreift.",
      "Ein Unternehmen, das Sachgüter produziert."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was ist das Sozialprodukt in der Volkswirtschaftlichen Gesamtrechnung?",
    "answers": [
      "Die Untersuchung und Darstellung des Wirtschaftsgeschehens einer Volkswirtschaft für eine abgelaufene Periode.",
      "Der Gesamtwert aller Sachgüter und Dienstleistungen in einem bestimmten Zeitabschnitt.",
      "Die Produktion von Gütern und Dienstleistungen durch private Haushalte."
    ],
    "correctAnswer": 1,
    "difficulty": 7
  },
  {
    "question": "Was umfasst die Makroökonomie?",
    "answers": [
      "Die Analyse des Verhaltens von Unternehmen.",
      "Die Untersuchung gesamtwirtschaftlicher Phänomene.",
      "Die Produktion von Gütern und Dienstleistungen."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was ist der Nutzen in der Marktlehre?",
    "answers": [
      "Das Ausmaß der individuellen Bedürfnisbefriedigung.",
      "Die Menge an Gütern, die bestimmte Wirtschaftsteilnehmer kaufen wollen.",
      "Die Veränderung des Gesamtnutzens durch eine weitere konsumierte Einheit eines Gutes."
    ],
    "correctAnswer": 0,
    "difficulty": 6
  },
  {
    "question": "Was sind private Haushalte?",
    "answers": [
      "Gemeinschaften, die keine Bedürfnisse haben.",
      "Wirtschaftsteilnehmer, die Geld durch Arbeit verdienen.",
      "Unternehmen, die Sachgüter produzieren."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was kritisiert man am BIP/BNE in der Volkswirtschaftlichen Gesamtrechnung?",
    "answers": [
      "Erfasst nicht: Schwarzarbeit, ehrenamtliche Arbeit, Kriminalität.",
      "Die Zusammensetzung spielt keine Rolle.",
      "Die Nachhaltigkeit der Produktion von Gütern."
    ],
    "correctAnswer": 0,
    "difficulty": 7
  },
  {
    "question": "Was ist der Gleichgewichtspreis auf einem Markt?",
    "answers": [
      "Ein Zustand, in dem es keine Nachfrage nach Gütern gibt.",
      "Der Preis, bei dem die nachgefragte Menge mit der angebotenen Menge übereinstimmt.",
      "Ein Preis, der vom Staat festgelegt wird."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was ist die Einkommenselastizität?",
    "answers": [
      "Die Veränderung des Grenznutzens bei steigendem Einkommen.",
      "Die Veränderung des Konsumverhaltens bei Veränderung des Einkommens.",
      "Die Höhe des Brutto Inlands Produkts (BIP)."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was ist der Zusatznutzen in der Marktlehre?",
    "answers": [
      "Die Veränderung des Gesamtnutzens durch eine weitere konsumierte Einheit eines Gutes.",
      "Die Menge an Gütern, die bestimmte Wirtschaftsteilnehmer verkaufen wollen.",
      "Die Veränderung des Einkommens bei steigendem Konsum."
    ],
    "correctAnswer": 0,
    "difficulty": 5
  },
  {
    "question": "Was sind Marktungleichgewichte?",
    "answers": [
      "Ein Zustand, in dem es keine Nachfrage nach Gütern gibt.",
      "Ein Zustand, in dem die nachgefragte Menge größer ist als die angebotene Menge.",
      "Der Preis, bei dem die nachgefragte Menge mit der angebotenen Menge übereinstimmt."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was sind Sozial- und Kulturbedürfnisse?",
    "answers": [
      "Bedürfnisse, die lebensnotwendig sind.",
      "Bedürfnisse, die den Lebensstandard erhöhen.",
      "Bedürfnisse, die keinen Einfluss auf das Lebensgefühl haben."
    ],
    "correctAnswer": 1,
    "difficulty": 4
  },
  {
    "question": "Was charakterisiert den Polypol-Markt?",
    "answers": [
      "Eine geringe Anzahl von Marktteilnehmern und eingeschränkte Konkurrenz.",
      "Viele Marktteilnehmer, freie Konkurrenz, freier Marktzugang, Informationsgleichstand.",
      "Einer allein hat alle Marktanteile."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Welche Gefahr besteht im Oligopol-Markt?",
    "answers": [
      "Gefahr von niedrigen Preisen.",
      "Gefahr von Absprachen und Kartellen.",
      "Gefahr von unkontrollierter Konkurrenz."
    ],
    "correctAnswer": 1,
    "difficulty": 7
  },
  {
    "question": "Was kennzeichnet den Monopol-Markt?",
    "answers": [
      "Freier Marktzugang für alle Anbieter.",
      "Viele Anbieter und freie Konkurrenz.",
      "Einer allein hat alle Marktanteile."
    ],
    "correctAnswer": 2,
    "difficulty": 5
  },
  {
    "question": "Was sind Beispiele für Kartelle?",
    "answers": [
      "Preiskartelle im Supermarkt.",
      "Mengenkartelle in der OPEC für Erdöl.",
      "Regionale Kartelle für Strom und Rauchfangkehrer."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was definiert einen vollkommenen Markt?",
    "answers": [
      "Wenn die Güter nach Art der Beschaffung ident sind.",
      "Wenn es keine Präferenzen bezüglich bestimmter Käufer und Verkäufer gibt.",
      "Wenn es keine räumliche oder zeitliche Differenzierung zwischen Angebot und Nachfrage gibt."
    ],
    "correctAnswer": 2,
    "difficulty": 5
  },
  {
    "question": "Wann spricht man von einem unvollkommenen Markt?",
    "answers": [
      "Wenn die Güter nach Art der Beschaffung ident sind.",
      "Wenn nicht alle oder keine der vollkommenen Markt-Kriterien erfüllt sind.",
      "Wenn es keine räumliche oder zeitliche Differenzierung zwischen Angebot und Nachfrage gibt."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was sind Produktionsfaktoren in der Volkswirtschaft?",
    "answers": [
      "Nur die eingesetzten Maschinen und Werkzeuge.",
      "Die eingesetzten Mittel für die Produktion von Sachgütern oder Dienstleistungen.",
      "Nur die finanziellen Ressourcen eines Unternehmens."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was sind Standortfaktoren in der Betriebswirtschaft?",
    "answers": [
      "Nur betriebswirtschaftliche Faktoren ohne räumlichen Bezug.",
      "Betriebswirtschaftliche Faktoren an einem bestimmten Ort, die die Wirtschaftlichkeit eines Unternehmens beschreiben.",
      "Nur die harten Standartfaktoren."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Was sind harte Standortfaktoren?",
    "answers": [
      "Faktoren mit direktem Einfluss auf den Gewinn, wie Qualität der Mitarbeiter und Produktionskosten.",
      "Faktoren mit indirektem Einfluss auf den Gewinn, wie Werbung und Trends.",
      "Faktoren, die keine Auswirkungen auf den Gewinn haben."
    ],
    "correctAnswer": 0,
    "difficulty": 7
  },
  {
    "question": "Was sind weiche Standortfaktoren?",
    "answers": [
      "Faktoren mit direktem Einfluss auf den Gewinn, wie Qualität der Mitarbeiter und Produktionskosten.",
      "Faktoren mit indirektem Einfluss auf den Gewinn, wie Werbung und Trends.",
      "Faktoren, die keine Auswirkungen auf den Gewinn haben."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Welche Argumente sprechen für den Wirtschaftsstandort Österreich?",
    "answers": [
      "Hohe Lohn- und Lohnnebenkosten.",
      "Zentrale Lage, gute Infrastruktur, gutes Sozialsystem.",
      "Binnenstaat und niedrige Steuern."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  },
  {
    "question": "Welche Argumente sprechen gegen den Wirtschaftsstandort Österreich?",
    "answers": [
      "Hohe Lohn- und Lohnnebenkosten.",
      "Zentrale Lage, gute Infrastruktur, gutes Sozialsystem.",
      "Binnenstaat und niedrige Steuern."
    ],
    "correctAnswer": 0,
    "difficulty": 6
  },
  {
    "question": "Was sind Produktions- und Standortfaktoren?",
    "answers": [
      "Nur betriebswirtschaftliche Faktoren ohne räumlichen Bezug.",
      "Die eingesetzten Mittel für die Produktion von Sachgütern oder Dienstleistungen.",
      "Nur die harten Standartfaktoren."
    ],
    "correctAnswer": 1,
    "difficulty": 5
  },
  {
    "question": "Was versteht man unter einem Mengenkartell?",
    "answers": [
      "Ein Kartell, das Mengenrabatte für Konsumenten anbietet.",
      "Ein Kartell, das den Markt durch hohe Preise kontrolliert.",
      "Ein Kartell, das die Menge der produzierten Güter beschränkt, um Preise zu kontrollieren."
    ],
    "correctAnswer": 2,
    "difficulty": 7
  },
  {
    "question": "Was sind Beispiele für Mengenkartelle?",
    "answers": [
      "Bierkartell und Supermarktketten.",
      "OPEC für Erdöl und Bierkartell.",
      "OPEC für Erdöl und Bierkartell."
    ],
    "correctAnswer": 1,
    "difficulty": 6
  }
]





const randomQuestions = () => {
  // return questions_container.slice(2, 12);
  let questions_n: Question[] = [];
  while (questions_n.length < 10) {
    let rand_idx = Math.floor(Math.random() * questions_container.length);
    if (questions_n.includes(questions_container[rand_idx])) continue;
    questions_n.push(questions_container[rand_idx]);
  }
  return questions_n.sort((a, b) => a.difficulty - b.difficulty)
}

const questions = randomQuestions();
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
      <Question :idx="idx" :question="currentQuestion.question" :answers="currentQuestion.answers"
        :question_length="questions.length" :correctAnswer="currentQuestion.correctAnswer" @answer="handleAnswer" />
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

<style scoped>#btmslider {
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
}
</style>
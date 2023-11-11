<script setup lang="ts">

onMounted(() => {
    const audio = new Audio('/MillionWinsound.mp3');
    // audio
    audio.play();
})

</script>

<template>
    <main>
        <h1 id="winHeadlne">Sie haben eine Million Euro gewonnen!!!!</h1>
        <h3>§ (Abzüglich Steuern und Gebühren bleibt Ihnen ein Gewinn im Wert eines Fizzers.)</h3>
    </main>
</template>

<style scoped>
h1 {
    color: rgb(0, 255, 0);
    text-align: center;
    animation: growHeadlne 15s forwards;
}
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
}
h3, h1 {
    padding: 1rem;
    text-align: center;
}

@keyframes growHeadlne {
    0% {
        font-size: 0.1rem;
    }
    100% {
        font-size: 4rem;
    }
}
</style>
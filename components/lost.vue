<script lang="ts" setup>
const props = defineProps({
    score: Number,
})

// onMounted(() => {
//     const audio = new Audio('/wah-wah-sound-effect.mp3');
//     // audio
//     audio.play();
// })
</script>

<template>
    <main>
        <h1>Du hast es bis zum level {{ score }} geschafft!</h1>
        <h2>Vielleicht klappt es beim nächsten Mal!</h2>
    </main>
</template>

<style scoped>
h1 {
    color: rgb(255, 196, 0);
    text-align: center;
}
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
}
</style>
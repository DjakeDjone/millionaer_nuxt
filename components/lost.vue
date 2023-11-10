<script lang="ts" setup>
const props = defineProps({
    score: Number,
})
</script>

<template>
    <main>
        <h1>Du hast es bis zum level {{ score }} geschafft!</h1>
        <h2>Vielleicht klappt es beim nächsten mal!</h2>
    </main>
</template>

<style scoped>
h1 {
    color: red;
}
main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
}
</style>
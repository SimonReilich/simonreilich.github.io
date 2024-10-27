<script setup>
</script>

<script>
export default {
    data() {
        return {
            ls: [
                { title: "Accordion", date: "2014 - now", image: "/public/accordion.jpg", text: "I've also been very passionate about music for a long time, playing the accordion since 2nd grade. Having played in many different line-ups, from solo over band to a classical orchestra, I learned many things in the past years. I've also been to multiple competitions, including the World Music Festival in Insbruck in 2016 and 2019 (and most likely 2025 again)." },
                { title: "Leader of TheJoCraft's Building-Team", date: "2021 - now", image: "/public/tjc.png", text: "I am a member of the Team of the german \"Minecraft\"-Youtuber \"TheJoCraft\" (team.tjcteam.de/), leading the team since summer of 2023. I not only enjoy beeing creative sometimes, but also like working together with other pepole. We've tackled many different projects as a team together, some of them you can see at my other website red-pixl.github.io/" }
            ]
        }
    }
}
</script>

<template>
    <div class="c2">
        <h2>Other</h2>

        <div v-for="e in ls" class="container">
            <div>
                <h3>{{ e.title }}</h3>
                <p>{{ e.date }}</p>
                <p>{{ e.text }} </p>
            </div>
            <img :src="e.image" alt="">
        </div>
    </div>
</template>

<style scoped>
.c2 {
    max-width: 80rem;
    width: 100vw;
    margin-inline: auto;
}

h2 {
    margin: 2rem;
    margin-top: 6rem;
    font-size: 4svh;
}

p,
h3 {
    margin: 2rem;
    font-size: 1.25rem;
}

.container {
    max-width: 80rem;
    width: 100vw;
    margin-inline: auto;
}

img {
    margin: 2rem;
    width: calc(100vw - 4rem);
    max-width: 20rem;
    height: calc(100vw - 4rem);
    max-height: 20rem;
    border-radius: 2rem;
    box-shadow: 0px 10px 30px 4px rgba(0, 0, 0, 0.2);
}

@media only screen and (min-width: 1000px) {
    .container {
        display: flex;
    }
}

@media only screen and (max-width: 1000px) {
    img {
        max-width: 30rem;
        max-height: 30rem;
        margin-inline: 0rem;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
        margin-top: 0rem;
    }
}
</style>
<script setup>
</script>

<script>
export default {
    data() {
        return {
            ls: [
                { title: "42. Bundeswettbewerb Informatik, First Round, First Price", date: "Fall 2023", image: "/public/bwinf.png", text: "Held by \"Gesellschaft für Informatik e.V.\", \"Fraunhofer-Verbund IUK-Technologie\", and the \"Max-Planck-Institut für Informatik\", the \"Bundeswettbewerb Informatik\", BWInf for short, is one of the largest German computer-science competitions. Learn more at https://bwinf.de/" }
            ]
        }
    }
}
</script>

<template>
    <div class="c2">
        <h2>Achievements</h2>

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
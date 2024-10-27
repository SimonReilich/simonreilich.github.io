<script setup>
</script>

<script>
export default {
    data() {
        return {
            cv: [
                { title: "Werner Heisenberg Gymnasium Garching, TUMKolleg", date: "Sep. 2024 - Summer 2026", image: "/whg.jpg", text: "Specialties of TUMKolleg: 3 natural sciences (Advanced Level physics, computer science, and chemistry), the W-Seminar is replaced by a scientific report written at TUM; Supervisor and Chair will be choosen in the winterhollidays of 2024/2025; For more information regarding the TUMKolleg and reports from the visits to the different departments, see tumkolleg.de/" },
                { title: "Pre-college Student at TUM", date: "Sep. 2022 - Summer 2026", image: "/tum.jpg", text: "Visiting regular lectures and tutorials at the Technical University of Munich, mainly compulsory courses from the computer science curriculum, grades can be credited towards a later study at TUM; I have already collected 61 ECTS (out of 180) with an average of 2.4, and am doing an additional 11 during the current semester; For more information, see schueler.in.tum.de/" },
                { title: "Viscardi Gymnasium Fürstenfeldbruck", date: "Sep. 2017 - Aug. 2024", image: "/viscardi.jpg", text: "Scientific technological branch, Latin as second forgein language, practical seminar „Arranging a piece of music“ in the subject music; Played in the school-orchestra for 5 years; Average of 1.3 in the last year" }
            ],
        }
    }
}
</script>

<template>
    <div class="container">
        <h2>Education</h2>
        <div class="line">
            <div class="entry" v-for="e in cv">
                <div class="point"></div>
                <div class="entry_text">
                    <div>
                        <h3>{{ e.title }}</h3>
                        <p>{{ e.date }}</p>
                        <p>{{ e.text }} </p>
                    </div>
                    <img :src="e.image" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
h2 {
    margin: 2rem;
    margin-top: 6rem;
    font-size: 4svh;
}

.container {
    max-width: 80rem;
    width: 100vw;
    margin-inline: auto;
}

.line {
    width: 1rem;
    height: fit-content;
    margin: 1rem;
    margin-left: 2.5rem;
    background-color: #B2AAC2;
    border-radius: 1rem;
    overflow: visible;
}

.entry {
    display: flex;
    align-items: left;
    flex-direction: row;
    width: calc(min(80rem, 100vw) - 8.5rem);
    margin: 1rem;
    overflow: visible;
}

.point {
    position: absolute;
    transform: translate(-1.5rem, 3.75rem);
    width: 1rem;
    height: 1rem;
    border-radius: 50%;
    border: 0.5rem solid #B2AAC2;
    background-color: #F2F2F2;
}

.entry_text {
    position: relative;
    transform: translateX(3rem);
    font-size: 1.25rem;
    max-width: 100%;
    overflow-wrap: break-word;
}

img {
    margin-top: 1.5rem;
    width: calc(100vw - 8.5rem);
    max-width: 20rem;
    height: calc(100vw - 8.5rem);
    max-height: 20rem;
    border-radius: 2rem;
    box-shadow: 0px 10px 30px 4px rgba(0, 0, 0, 0.2);
}

@media only screen and (min-width: 1000px) {
    .entry_text {
        display: flex;
        gap: 2rem;
    }
}

@media only screen and (max-width: 1000px) {
    img {
        position: relative;
        max-width: 30rem;
        max-height: 30rem;
    }
}
</style>
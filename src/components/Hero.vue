<script setup>
</script>

<script>
export default {
    data() {
        return {
            texts: ['a Programmer', 'a Mathematician', 'a Musician', 'an Architect', 'a Student', 'a Scientist', 'Simon Reilich'],
            text: '|',
            animation_lock: false
        }
    },
    methods: {
        animate (text_number, char_number) {
            this.text = this.texts[text_number].slice(0, char_number) + '|';
            if (text_number != this.texts.length - 1) {
                if (char_number < this.texts[text_number].length) {
                    setTimeout(() => {
                        this.animate(text_number, char_number + 1);
                    }, 50);
                } else {
                    setTimeout(() => {
                        this.animate(text_number + 1, 0);
                    }, 250);
                }
            } else if (char_number != this.texts[this.texts.length - 1].length) {
                setTimeout(() => {
                    this.animate(text_number, char_number + 1);
                }, 100);
            } else {
                setTimeout(() => {
                    this.text = this.texts[text_number];
                    document.documentElement.style.overflowY = 'auto';
                    setTimeout(() => {
                        this.animation_lock = false;
                    }, 10000);
                }, 250);
            }
        },

        start_animation() {
            if (!this.animation_lock) {
                this.animation_lock = true;
                this.animate(0, 0);
            }
        }
    },
    mounted() {
        setTimeout(() => {
            this.start_animation();
        }, 250);
        document.documentElement.style.overflow = 'hidden';
    }
}
</script>

<template>
    <h1 class="poppins-bold" @mouseenter="start_animation()">Hi, I'm <br> {{ text }} <br> <button>Threads</button> <button>GitHub</button> <button>LinkedIn</button> </h1>
    <img src="/public/main.png">
    <div></div>
</template>

<style scoped>
h1 {
    z-index: 20;
}

button {
    width: 7em;
}

img {
    z-index: 10;
}

@keyframes fadeIn {
        0% {
            opacity: 0%;
        }
        80% {
            opacity: 0%;
        }
        100% {
            opacity: 100%;
        }
    }

div {
    width: 100vw;
    height: 100svh;
    z-index: -10;
    animation: 10s ease-out 0s 1 fadeIn;
}

button {
    transition: ease-in-out 0.2s;
    border: none;
    outline: none;
}

button:hover {
    cursor: pointer;
    transform: scale(1.075);
    box-shadow: 0px 10px 30px 4px rgba(0,0,0,0.2);
    border: none;
    outline: none;
}

@media only screen and (max-width: 1500px) {
    h1 {
        text-align: center;
        font-size: min(10vw, 5rem);
        width: min(100vw, 50rem);
        height: min(40vw, 20rem);
        position: absolute;
        left: 50%;
        top: calc((100vh - min(100vw, 100vh - 25rem)) / 2.25);
        transform: translate(-50%, -50%);
    }

    button {
        width: min(25vw, 12.5rem);
        height: min(10vw, 5rem);
        font-size: min(3.5vw, 1.75rem);
        border-radius: min(4vw, 2rem);
    }

    @keyframes slideInFromBottom {
        0% {
            transform: translateY(100%);
        }
        70% {
            transform: translateY(100%);
        }
        100% {
            transform: translateY(0%);
        }
    }

    img {
        position: absolute;
        width: min(100vw, 100vh - 25rem);
        height: min(100vw, 100vh - 25rem);
        top: calc(100svh - min(100vw, 100vh - 25rem));
        left: calc((100vw - min(100vw, 100vh - 25rem)) / 2);
        animation: 8s ease-out 0s 1 slideInFromBottom;
    }

    div {
        margin-top: 0rem;
        background: radial-gradient(circle at bottom, #B2AAC2, transparent);
    }
}

@media only screen and (min-width: 1500px) {
    h1 {
        text-align: left;
        font-size: 6vw;
        position: absolute;
        left: max(5rem, calc(50vw - 60svh - 20rem));
        top: 40%;
        transform: translate(0%, -50%);
    }

    button {
        width: 10vw;
        height: 4vw;
        font-size: 1.5vw;
        border-radius: 1.6vw;
    }

    @keyframes slideInFromRight {
        0% {
            transform: translateX(120svh);
        }
        70% {
            transform: translateX(120svh);
        }
        100% {
            transform: translateX(20svh);
        }
    }

    img {
        position: absolute;
        margin: 0rem;
        padding: 0rem;
        right: 0svh;
        transform: translateX(20svh);
        width: 100svh;
        height: 100svh;
        animation: 8s ease-out 0s 1 slideInFromRight
    }

    div {
        background: radial-gradient(circle at right, #B2AAC2, transparent);
    }
}
</style>
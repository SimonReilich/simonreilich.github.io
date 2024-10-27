<script setup>
</script>

<script>
export default {
    data() {
        return {
            navPos: window.innerHeight,
            render: false,
        }
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll);
    },
    methods: {
        onScroll(e) {
            this.windowTop = e.target.documentElement.scrollTop;
            if (this.windowTop > window.innerHeight) {
                this.windowTop = window.innerHeight;
                this.render = true;
            } else if (this.render) {
                this.render = false;
            }
            this.navPos = window.innerHeight - this.windowTop;
        }
    }
}
</script>

<template>
    <div v-if="render" class="container" style="top: 0px; background-color: #f2f2f288;">
        <h3>Simon Reilich</h3>
        <img src="/public/menu.svg">
    </div>
    <div v-else class="container" style="position: absolute; background-color: #f2f2f2;">
        <h3>Simon Reilich</h3>
    </div>
    <div style="height: 10svh;" </div>
</template>

<style scoped>
.container {
    width: 100vw;
    height: 10svh;
    backdrop-filter: blur(15px);
    position: fixed;
    z-index: 10000000;
    box-shadow: 0px 10px 30px 4px rgba(0, 0, 0, 0.1);
}

h3 {
    position: absolute;
    top: 0svh;
    left: 3svh;
    font-size: 3svh;
}

@keyframes slideinFromRight {
    0% {
        transform: translateX(20svh);
    }

    100% {
        transform: translateX(0);
    }
}

img {
    position: absolute;
    top: 3.5svh;
    right: 3svh;
    width: 3svh;
    height: 3svh;
}
</style>
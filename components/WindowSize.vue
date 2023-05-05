<template>
    <div>
        <h1> Height Width </h1>
        <h2> {{ windowWidth }} x {{ windowHeight }} </h2>
    </div>
</template>

<script>

export default {
    title: "WindowSize",
    computed: {
        windowWidth() {
            return window.innerWidth;
        },
        windowHeight() {
            return window.innerHeight;
        }
    }
}

</script>
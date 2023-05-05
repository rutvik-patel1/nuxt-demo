<template>
    <div>
        <h1>{{ title }}</h1>
        <h2>About Page</h2>
    </div>
</template>
    
<script>
export default {
    data() {
        return {
            title: 'Hello World!'
        }
    },
    mounted() {
        this.$nextTick(() => {
            this.$nuxt.$loading.start()
            setTimeout(() => this.$nuxt.$loading.finish(), 3000)
        })
    },
    head() {
        return {
            title: this.title,
            meta: [
                // hid is used as unique identifier
                {
                    hid: 'description',
                    name: 'description',
                    content: 'My custom description'
                }
            ]
        }
    }
}
</script>
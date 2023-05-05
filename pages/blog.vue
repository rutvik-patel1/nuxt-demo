<template>
    <div>
        <h1>BLOG PAGE</h1>
    </div>
</template>

<script>
export default {
    name: 'BlogPage',
    layout:'blog',
    middleware: [
        'auth',
        function({redirect}){
           console.log("BACANCY")
            //    redirect('/')
        },
    ]

}

</script>
<template>
  <div>
    <h1>INDEX PAGE</h1>
    <client-only>
      <window-size></window-size>
  </client-only>
  {{ windowHeight }}
  </div>
</template>

<script>
export default {
  name: 'IndexPage',  

  computed:{

    windowHeight(){
      //global varibale
      if(process.client){
        return window.innerHeight
      }
    }

  }
}
</script>

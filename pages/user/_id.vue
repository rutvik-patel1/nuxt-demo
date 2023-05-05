<template>
    <div>
       USER_PARAMS: {{ $route.params.id }}
       <button @click="$fetch">REFRESH</button>
       <div class="profile">
        <img :src="userData.avatar_url" alt="Profile picture">
        <h1>{{ userData.login }}</h1>
        <p>{{ userData.bio }}</p>
        <ul>
          <li><strong>Followers:</strong> {{ userData.followers }}</li>
          <li><strong>Following:</strong> {{ userData.following }}</li>
          <li><strong>Public Repos:</strong> {{ userData.public_repos }}</li>
        </ul>
      </div>
    </div>
</template>

<script>
    export default {
        name:"Profile",

        data(){
            return {
                userData : []
            }
        },
        
        head(){
            return {
                title: 'User',
                meta :[
                    { hid: 'description', name: 'description', content: 'BACANCY' }
                ]
            }
        },

        validate(context){
            console.log("validate")
            console.log(context.route.params.id)
            if(context.route.params.id == 1) return true
            return false
        },

        async asyncData({$axios}){
            const userData = await $axios.$get('https://api.github.com/users/rutvik-patel1')
            console.log("async data hook")
            return {
                userData
            }
        },
        fetch(){
            console.log("fetch")
        },
        created(){
            console.log("in created")
        },
        mounted(){
            console.log("in mounted")
        },
        async fetch(){
            this.userData = await this.$axios.$get('https://api.github.com/users/rutvik-patel1')
        }
    }
</script>

<style>
.profile {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 20px;
  margin:20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

img {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin-bottom: 20px;
}

h1 {
  margin-bottom: 10px;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}

li {
  margin-bottom: 5px;
}
button {
  padding: 5px;
  border: 1px solid black;
}
</style>
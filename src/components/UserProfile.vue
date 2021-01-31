<template>
<div class="user-profile">
   @ {{user.username}} - {{fullname}}
   <br/> <span>Followers: </span> <strong>{{fellowers}}</strong>
  <br/> <button @click="followUser">Fellow</button>

</div>

</template>

<script>
export default {
  name: 'UserProfile',
   data(){
    return {
      fellowers:0,
      user:{
        id:1, 
        username: 'boakye51',
        firstname: 'boakye',
        lastname: 'kofi'

      }
    }
  },

  computed: {
    fullname(){
      return  `${this.user.firstname} ${this.user.lastname}`
    }
  },

  methods: {
    followUser() {
      this.fellowers ++  
    }
  } ,
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .user-profle{
   display: grid;
   grid-template-columns: 1fr 3fr;
   width: 50% 5%;
   padding: 50px 5%;

  
 }

  .user-profile__user-panel{
    display: flex;
    flex-direction: column;
    margin-right: 50px;
    padding: 20px;
    background-color: white;
    border-radius: 5px;
    border:1px solid #DFE3F8;
  }

  h1{
    margin:0px;
  }
</style>

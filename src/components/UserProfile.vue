<template>
<div class="user-profile">
  <div class="user-profile__user-panel">
    <h1 class="user-profile__username">
      @ {{user.username}}
    </h1>
    <div class="user-profile__admin-bage" v-if="user.isAdmin">
      Admin
    </div>
    <div class="user-profile__foller-count">
      <br/> <span>Followers: </span> <strong>{{fellowers}}</strong>
        <br/> <button @click="followUser">Fellow</button>
    </div>
 

   
  </div>

   <div class="twoots-wrapper">
     <TwootItem :key="index" v-for="(twoot, index) in user.twoots" :username="user.username" :twoot="twoot"/>
 </div>
</div>

</template>

<script>
import TwootItem from './TwootItem';
export default {
  name: 'UserProfile',
  components:{TwootItem},
   data(){
    return {
      fellowers:0,
      user:{
        id:1, 
        username: 'boakye51',
        firstname: 'boakye',
        lastname: 'kofi',
        email:"kbpayal@gmail.com",
        isAdmin:false,
        twoots:[
          {id:1, content: 'Twoteri is Amazing'},
          {id:2, content:"Don't forget to subscriber to the Earth is squre!"}
        ]

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
 .user-profile{
   display: grid;
   grid-template-columns: 1fr 3fr;
   width:100%;
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

  .user-profile__admin-bage{
    background: rebeccapurple;
    color: white;
    border-radius: 5px;
    margin-right: auto;
    padding: 0 10px;
    font-size: bold;
    margin-top: 10px;
  }
</style>

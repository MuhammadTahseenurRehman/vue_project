<template>
  <div class="hello">
    <div class="skills">

      <form @submit.prevent='addSkills'>
      <input type="text" placeholder="Enter a skills you have..." v-model="skill" v-validate="'min:5'" name="skill">
      <p class="alert" v-if="errors.has('skill')">{{ errors.first('skill') }}</p>
      </form>

      <ul>
        <li v-for="(data, index) in skills" :key='index'>{{data.skills}}</li>
      </ul>


      <!-- <p v-if="skills.length > 2">You have more than one skills</p>
      <p v-else>You hve one skill</p> -->

      <!-- <div v-bind:class="{ alert: showAlert, anotherClass:showClass }"></div> -->

      <!-- <div v-bind:class="alertObject"></div> -->
      
      <!-- <div v-bind:style=" {backgroundColor : bgColor, width: bgWidth, height: bgHeight}"></div> -->

      <p>These are the skills that you possess</p>

    </div>
  </div>
</template>

<script>
export default {
  name: 'skills',
  data(){
    return{
      skill:'',
      skills:[
        {"skills":'Designers'},
        {'skills':'Front end Developer'}
      ],
      // showAlert: true,
      // showClass: true,
      // alertObject: {
      //   alert:true,
      // },
      // bgColor: 'yellow',
      // bgWidth: '100px',
      // bgHeight: '40px'
    }
  },
  methods: {
    addSkills(){
      this.skills.push({skills: this.skill})
      this.skill= '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.alert{
  height: 30px;
  width: 100px;
  background-color: #42b983;
}
.anotherClass{
  border:1px solid #000;
} 
  .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  
  input{
    width: calc(100% - 40px);
    border: 0;
    padding:20px;
    font-size: 16px;
    background-color: #323232;
    color: #687f7f;
  }
</style>

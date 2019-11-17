<template>
  <div id="app">
    <!--@nextQuestion is sending a method as a prop -->
    <!--v-bind or :currentQuetion is sending a question a a prop -->
    <Questions @nextQuestion= "nextQuestion" v-bind:currentQuestion= questions[currentSpot] />
  </div>
</template>

<script>
import Questions from '@/components/Questions.vue';

export default {
  name: 'app',
  components: {
    Questions
  },
  //Similar to React state
  data(){
    return{
      //array of questions
      questions:[
        "What is the difference in 'Let' and 'Const'?",
        "What is the difference in '=' and '==' and '==='?",
        "What is a JSON?",
        "What is a variable?",
      ],
      //current question index
      currentSpot:0,
    }
  },
  methods:{
    //function to be passed down as a prop to update the current index in the array of questions
    nextQuestion(){
      if(this.currentSpot == this.questions.length-1){
        this.currentSpot = 0;
      }else {
        this.currentSpot ++;
      }      
    }
  }
}
</script>

<style>
</style>

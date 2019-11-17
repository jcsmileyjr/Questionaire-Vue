<template>
    <div id="questions">
        <!-- prop pass down from parent component -->
        <h1>{{currentQuestion}}</h1>
        <!-- click event that call a function -->
        <button @click="getNextQuestion">Next</button>
    </div>
</template>

<script>
export default {
    //name of component to be exported
    name: "questions",
    props: {
        //prop pass down from parent
        currentQuestion: String,
    },
    methods: {
        //function that calls another function that was pass down as a prop. 
        //It does not send data back up        
        getNextQuestion(){
            this.$emit('nextQuestion');
        }
    }
}
</script>

<style scoped>
    #questions {
        text-align: center;
    }

    div {
        
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        min-height: 100vh;

    }
</style>
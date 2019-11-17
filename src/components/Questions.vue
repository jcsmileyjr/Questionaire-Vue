<template>
    <div id="questions">
        <section>
        <h1>JavaScript Interview Questions</h1>
        <!-- prop pass down from parent component -->
        <h3>{{currentQuestion}}</h3>
        <!-- click event that call a function -->
        <button @click="getNextQuestion">Next</button>
        </section>
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
        
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background-color:#6A5555;

    }

    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        background-color: white;
        height: 50vh;
        width: 80vh;
    }

    h1 {
        color: navy;
    }

    button {
        background-color: green;
        font-size: 1.5rem;
        border: 1px solid green;
        border-radius: 5px; /*round out the corners of the button*/
        box-shadow: 2px 3px 4px grey; /*shadow under the button*/
    }
</style>
<template>
<div id="clock">
    <h1>{{ hours }}: </h1>
    <h1>{{ minutes }}: </h1> 
    <h1>{{ seconds }}</h1>
</div>

<div id="button-container">
    <button @click="sumHours()">
        Somar Horas
    </button>
    <button @click="decrHours()">
        Diminuir horas
    </button>
</div>


</template>

<script>
export default{
    name: "TimerMain",
    data() {
        return{
            hours: '00',
            minutes: '00',
            seconds: '00',

        }
    },
    methods: {
        sumHours(){
            if(this.hours<24){
            this.hours ++
            }else{
                this.hours = 0
            }
        }
        
    }
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@300&family=Poppins:wght@200;400&display=swap');

    #clock{
        display: flex;
        width: min-content;
        background-color: rgb(233, 186, 255);
        padding: 5vh;
    }

    h1{
        font-size: 4em;
        font-family: 'Inconsolata', monospace;
        font-family: 'Poppins', sans-serif;
    }

   
</style>
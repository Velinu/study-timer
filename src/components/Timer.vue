<template>
    <div id="main-container">
        <div id="clock">
            <h1>{{ hours }}: </h1>
            <h1>{{ minutes }}: </h1> 
            <h1>{{ seconds }}</h1>
        </div>

    </div>


</template>

<script>

export default{
    name: "TimerMain",
    props: {
        hours: Number,
        minutes: Number,
        seconds: Number
    }
     
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@300&family=Poppins:wght@200;400&display=swap');
    #main-container{
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    #clock{
        display: flex;
        width: min-content;
    }

    h1{
        font-size: 4em;
        font-family: 'Inconsolata', monospace;
        font-family: 'Poppins', sans-serif;
    }
   
</style>
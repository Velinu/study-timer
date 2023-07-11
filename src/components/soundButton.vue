<template>
    <div id='sound-button-container'>
        <img id='icon' :src="icon">
        <audio :src="sound"></audio>
        <input type="range" min="0" max="100" value="50" name="" id="">
        
        <button>
            <img src="/icons/play.png" alt="">
        </button>
    </div>
</template>

<script>
    export default{
        name: "soundButton",
        props: {
            sound: String,
            icon: String
        }
    }
</script>

<style scoped>
    #sound-button-container{
        display: flex;
        flex-direction: column;
        width: 10vw;
        height: 30vh;
        align-items: center;
        background-color: rgb(255, 248, 248);
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        border-radius: 10px;
    }

    #icon{
        width: 4vw;
        margin-top: 5vh;
        margin-bottom: 3vh;
    }

    input[type='range']{
        
        margin-bottom: 3vh;
    }

    button{
        height: 6vh;
        width: 3vw;
        border-radius: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
        border: none;
        background-color: rgb(255, 248, 248);
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        cursor: pointer;
        transition: 0.2s ease-in-out;
    }
    button:hover{
        background-color: rgb(255, 194, 255);
    }

    button img{
        height: 2vh;
        width: 1vw;
        margin: none;
    }

    

</style>
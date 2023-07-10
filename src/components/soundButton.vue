<template>
    <button id="sound-button-container">
        <img :src="icon">
        <input type="range" min="0" max="100" value="50" name="" id="">
    </button>
</template>

<script>
    export default{
        name: "soundButton",
        props: {
            track: String,
            icon: String
        }
    }
</script>

<style scoped>
    #sound-button-container{
        display: flex;
        flex-direction: column;
    }

    img{
        height: 5vh;
    }

    

</style>
<template>
    <div id="radio-container">
        <iframe id="radio" 
            width="50%" 
            height="20%"
            :src="radioURL" 
            frameborder="0"
            scrolling="auto"
            allowfullscreen
        ></iframe>
    </div>
</template>

<script>
    export default {
        name: "radioIframe",
        props: {
            radioURL: String
        }
    }
</script>

<style>
    #radio-container{
        margin: 1%;
        display: flex;
        justify-content: center;
    }

    #radio{
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    }
</style>
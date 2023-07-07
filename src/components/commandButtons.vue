<template>
    <button>
        <img :src="iconComBtn" :alt="altComBtn" >
    </button>
</template>

<script>
    export default{
        name: "commandButton",
        props: {
            iconComBtn: String,
            altComBtn: String,
        },
    }
</script>

<style scoped>
    button{
        background-color: rgb(255, 248, 248);
        border: none;
        padding: 1vw;
        border-radius: 50%;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        transition: 0.2s ease-in-out;
    }
    img{
        height: 2.5vh;
    }

    button:hover{
        cursor: pointer;
        background-color: rgb(255, 194, 255);
        transition: 0.2s ease-in-out;
    }
</style>


<template>
    <header>
        <div id="logo-container">
            <img class="logos" src="../assets/Logo.png" alt="logo">
            <h1>Study Timer</h1>
        </div>

        <div id="contact-container">
            <h1>Minhas redes</h1>
            <a href="https://www.linkedin.com/in/matheus-felinto-da-silva-6b5072233/">
                <img class="logos" src="../assets/linkedin.png" alt="Linkedin">
            </a>

            <a href="https://github.com/Velinu">
                <img class="logos" src="../assets/github.png" alt="Github">
            </a>
        </div>
    </header>
</template>

<script>
    export default{
        name: "headerComponent",

    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@300&family=Poppins:wght@200;400&display=swap');
    
    header{
        font-family: 'Inconsolata', monospace;
        font-family: 'Poppins', sans-serif;
        border-bottom: 3px solid black;
        display: flex;
        width: 80vw;
        margin-left: 10vw;
        justify-content: end;
        align-items: center;
        font-size: 15px;
        user-select: none;
    }

    #logo-container{
        height: 10vh;
        display: flex;
        align-items: center;
        margin-left: 2vw;
        user-select: none;
        width: 100%;
        justify-content: start;
    }

    .logos{
        height: 5.5vh;
        width: 3vw;
        margin-right: 1vw;
    }

    #contact-container{
        display: flex;
        align-items: center;
        text-align: center;

    }

    #contact-container h1{
        width: 15vw;
    }

</style>
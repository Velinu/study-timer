<template>
    <div id="sound-button-container">
      <img id="icon" :src="icon">
      <input id="range-imp" type="range" min="0" max="100" v-model="audioValue" @input="changeVolume" name="">
  
      <button @click.prevent="toggleAudio">
        <img :src="playBtnIcon" alt="">
      </button>
  
      <audio ref="audioSrc">
        <source :src="sound">
      </audio>
    </div>
  </template>
  
  <script>
  export default {
    name: "soundButton",
    props: {
      sound: String,
      icon: String
    },
    data() {
      return {
        isPlaying: false,
        playBtnIcon: '/icons/play.png',
        audioElement: null,
        audioValue: 0
      }
    },
    mounted() {
      this.audioElement = this.$refs.audioSrc;
    },
    methods: {
      toggleAudio() {
        if (this.isPlaying) {
          this.audioElement.pause();
          this.playBtnIcon = '/icons/play.png';
        } else {
          this.audioElement.play();
          this.playBtnIcon = '/icons/pause.png';
        }
        this.isPlaying = !this.isPlaying;
      },
      changeVolume() {
        this.audioElement.volume = this.audioValue / 100
      }
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

    #range-imp{
        --webkit-appearance: none;
        width: 80%;
        height: 0.1em;
        outline: none;
        border-radius: 5px;
    }


</style>
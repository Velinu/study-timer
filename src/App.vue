<template>
  <headerComponent />

  <main>
    <TimerMain :hours="formatTime(hours)" :minutes="formatTime(minutes)" :seconds="formatTime(seconds)" />
    
    <div id="command-buttons">
      
      <commandButton @click="playTimer()" :iconComBtn="playSrc" altComBtn="Play Time Button" />
      <commandButton @click="resetTimer()" iconComBtn="/icons/reset.png" altComBtn="Reset Time Button" />

      

      <commandButton @click="addHours()" iconComBtn="/icons/addHour.png" altComBtn="Add Hours Button" />
      <commandButton @click="decrHours()" iconComBtn="/icons/decrHour.png" altComBtn="Decrement Hours Button" />

    </div>

    <searchTrack />

  </main>

</template>

<script>
import TimerMain from './components/Timer.vue'
import headerComponent from './components/Header.vue'
import commandButton from './components/commandButtons.vue'
export default {
  name: 'App',
  data() {
    return {
      hours: 0,
      minutes: 0,
      seconds: 0,
      timer: null,
      isPlayng: true,
      playSrc: '/icons/play.png'
    }
  },

  components: {
    TimerMain,
    headerComponent,
    commandButton,
  },

  methods: {
    playTimer(){
        if(this.isPlayng == false){
          this.playSrc = '/icons/pause.png'
          this.isPlayng = !this.isPlayng

          this.timer = setInterval(() => {
            if (this.seconds > 0) {
              this.seconds--;
            } else {
              if (this.minutes > 0) {
                this.minutes--;
                this.seconds = 59;
              } else {
                if (this.hours > 0) {
                  this.hours--;
                  this.minutes = 59;
                  this.seconds = 59;
                } else {
                  clearInterval(this.timer);
                }
              }
            }
          }, 1000);
        }else{
          this.playSrc = '/icons/play.png'
          clearInterval(this.timer)
          this.isPlayng = !this.isPlayng
        }
    },
    
    resetTimer(){
      this.hours = 0
      this.minutes = 0
      this.seconds = 0
    },
    addHours(){
      if(this.hours < 24){
        this.hours ++
      }else{
        alert('Maximo de horas')
      }
    },

    decrHours (){
      if(this.hours>0){
        this.hours --
      } else{
        alert('Horas zeradas')
      }
    },

    formatTime(time){
      return time < 10 ? `0${time}` : time
    }
  }
  
}
</script>

<style>
  body{
    margin: 0;
  }

  #command-buttons{
    display: flex;
    justify-content: center;
  }

  #command-buttons button{
    margin: 1.5vw;
    margin-top: 0;
  }
</style>

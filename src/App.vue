<template>
  <headerComponent />

  <main>
    <TimerMain :hours="formatTime(hours)" :minutes="formatTime(minutes)" :seconds="formatTime(seconds)" />
    
    <div id="command-buttons">
      <commandButton @click="playTimer()" iconComBtn="/icons/play.png" altComBtn="Play Button" />
      <commandButton @click="resetTimer()" iconComBtn="/icons/pause.png" altComBtn="Reset Time Button" />

      <commandButton @click="addHours()" iconComBtn="/icons/addHour.png" altComBtn="Add Hours Button" />
      <commandButton @click="decrHours()" iconComBtn="#" altComBtn="Decrement Hours Button" />
    </div>

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
      timer: null
    }
  },

  components: {
    TimerMain,
    headerComponent,
    commandButton
  },
  methods: {
    playTimer(){
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
    margin: 2.5vw;
    margin-top: 0;
  }
</style>

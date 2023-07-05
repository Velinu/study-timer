<template>
<div id="clock">
    <h1>{{ hours }}:</h1>
    <h1>{{ minutes }}:</h1> 
    <h1>{{ seconds }}</h1>
</div>
</template>

<script>
export default{
    name: "TimerMain",
    data() {
        return{
            hours: '00',
            minutes: '00',
            seconds: '00'
        }
    },
    methods: {
        
    }
}
</script>

<style scoped>
    #clock{
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>
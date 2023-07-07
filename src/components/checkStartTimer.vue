<template>
    <div>
        <label>
        <input type="checkbox" :checked="isChecked" @change="handleCheckboxChange" hidden>
        <img :src="isChecked ? '/icons/play.png' : '/icons/pause.png'" alt="Checkbox Image">
        </label>

    </div>
  </template>
  
  <script>
  export default {
    props: {
      value: Boolean
    },
    computed: {
      isChecked: {
        get() {
          return this.value;
        },
        set(newValue) {
          this.$emit('input', newValue);
        }
      }
    },
    methods: {
      handleCheckboxChange(event) {
        this.isChecked = event.target.checked;
      }
    }
  };
  </script>

<style>
    input[type=checkbox]{
        background-color: rgb(247, 72, 72);
        border: none;
        width: 1vw;
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


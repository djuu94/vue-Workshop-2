<template>
    <div class="wrapper">
      <h2>{{ cardData.name }}</h2>
      <p>City: {{ cardData.city }}</p>
      <button @click="handleButtonClick">
        <slot>See how many titles {{ cardData.name }} has</slot>
      </button>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      cardData: {
        type: Object,
        required: true,
      },
    },
    methods: {
      handleButtonClick() {
        this.$emit('button-clicked', this.cardData.titles);
      },
    },
  };
  </script>
<style scoped>
.wrapper {
  list-style-type: none; 
  margin-bottom: 10px;  
  padding: 10px; 
  height:250px;
  width:180px;
  color:black;
  font-size: 16px;
  display:flex;
  flex-direction: column;
  border:1px solid black;
  background-color: #cbcbe43a; 
}
.wrapper button{
    font-size: 14px;
    text-align: center;
    background-color: #b4b4dd80; 
    border-radius: 3px;
    border:1px solid black;
    justify-self: end;
}


</style>
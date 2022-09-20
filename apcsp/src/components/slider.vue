<template>
    <div>
      <transition-group name="fade" tag="div">
        <div>
          <h2>{{ name }}</h2>
      <img v-bind:src="image" class="image" alt="clothing images" />
      <p>{{ desc }}</p>
        </div>
      </transition-group>
    </div>
  </template>
  
  <script>
  export default {
    name: "Slider",
    props: {
      name: String,
      type: String,
      image: String,
      desc: String,
    },
    
  };
  
  </script>
  
<style scoped>
      .image {
  width: 12rem;
  height: 12rem;
}
  </style>
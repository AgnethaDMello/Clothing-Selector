<template>
    <div v-bind:class="id">
      <h2>{{ name }}</h2>
      <img v-bind:src="img" class="image" alt="clothing images" />
      <p>{{ desc }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: "Card",
    props: {
      name: String,
      type: String,
      img: String,
      desc: String,
    },
  };
  </script>

  <style>
    .image {
  width: 12rem;
  height: 12rem;
}
  </style>
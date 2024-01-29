<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h2>Logout</h2>
      <button @click="logout">Logout</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      logout() {
        // Add logout logic here
        console.log('Logout button clicked');
      },
    },
  };
  </script>
  
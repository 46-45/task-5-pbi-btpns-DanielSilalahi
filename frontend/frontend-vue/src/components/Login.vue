<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="login-container">
      <h2>Login</h2>
      <form @submit.prevent="login">
        <label for="username">Username:</label>
        <input type="text" v-model="username" required>
  
        <label for="password">Password:</label>
        <input type="password" v-model="password" required>
  
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';

    export default {
    data() {
      return {
        username: '',
        password: '',
      };
    },
    methods: {
      login() {
        const loginData = {
          username: this.username,
          password: this.password,
        };

        axios.post('http://localhost:8080/login', loginData)
          .then(response => {
            // Handle successful login
            console.log('Login successful', response.data);
          })
          .catch(error => {
            // Handle login error
            console.error('Login failed', error.response.data);
          });
      },
    },
  };

  </script>
  
  <style scoped>
  .login-container {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  
  label {
    font-weight: bold;
  }
  
  input {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  
  button {
    padding: 10px;
    background-color: #3498db;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #2980b9;
  }
  </style>
  
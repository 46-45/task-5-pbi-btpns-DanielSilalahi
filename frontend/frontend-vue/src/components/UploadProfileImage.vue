<template>
    <div class="upload-profile-image-container">
      <h2>Upload Profile Image</h2>
      <input type="file" @change="handleFileChange">
      <button @click="uploadImage">Upload Image</button>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        // Your data fields go here
      };
    },
    methods: {
      uploadImage() {
        const imageUploadData = {
          // Your image upload data fields go here
        };
  
        axios.post('http://localhost:8080/post-image', imageUploadData)
          .then(response => {
            // Handle successful image upload
            console.log('Image upload successful', response.data);
          })
          .catch(error => {
            // Handle image upload error
            console.error('Image upload failed', error.response.data);
          });
      },
    },
  };
  </script>
  
  <style scoped>
  .upload-profile-image-container {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  input {
    margin-bottom: 10px;
  }
  
  button {
    padding: 10px;
    background-color: #f39c12;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #d35400;
  }
  </style>
  
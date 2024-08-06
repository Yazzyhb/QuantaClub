<template>
    <div class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <h2>{{ event.title }}</h2>
        <p>{{ event.date }}</p>
        <img :src="event.image" alt="Event Image" />
        <p>{{ event.details }}</p>
        <button @click="closeModal">Close</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      event: {
        type: Object,
        required: true
      }
    },
    methods: {
      closeModal() {
        this.$emit('close');
      }
    }
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }
  
  .modal-content {
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    width: 80%;
    max-width: 600px;
    position: relative;
  }
  
  .modal-content img {
    width: 100%;
    border-radius: 10px;
  }
  
  button {
    background: #007bff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background: #0056b3;
  }
  </style>
  
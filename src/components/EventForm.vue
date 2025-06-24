<template>
  <form @submit.prevent="handleSubmit">
    <label for="name">Name:</label>
    <input id="name" v-model="formData.name" required />

    <label for="email">E-Mail:</label>
    <input id="email" v-model="formData.email" type="email" required />

    <label for="message">Nachricht:</label>
    <textarea id="message" v-model="formData.message" required></textarea>

    <button type="submit">Absenden</button>
  </form>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const formData = reactive({
  name: '',
  email: '',
  message: '',
})

function handleSubmit() {
  console.log('Formulardaten:', formData)
  alert(`Danke, ${formData.name}! Wir haben deine Nachricht erhalten.`)
}
</script>

<style scoped lang="scss">
form {
  display: flex;
  flex-direction: column;
  width: 300px;
  gap: 0.5rem;
  margin: 2rem auto;
  font-family: sans-serif;

  input,
  textarea {
    padding: 0.5rem;
    border-radius: 6px;
    border: 1px solid #ccc;
  }

  button {
    background-color: #8942b8;
    color: white;
    padding: 0.5rem;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    transition: background 0.2s;

    &:hover {
      background-color: #339966;
    }
  }
}
</style>

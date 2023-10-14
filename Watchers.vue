<script>
import {ref, watch } from 'vue'

export const user = ref({
  name: 'John Doe',
  age: 30,
})

const birthYear = watch(() => {
  return new Date().getFullYear() - user.value.age
})

const canVote = watch(() => {
  if (user.value.age >= 18)
  {
      console.log('eligible for voting')
  }
  else
  {
      console.log('not eligible for voting')
  }
})


</script>

<template>
  <div>
    <h1>User Profile</h1>
    <p>Name: {{ user.name }}</p>
    <p>Age: {{ user.age }}</p>
    <p>Birth Year: {{ birthYear }}</p>
    <p>Can Vote: {{ canVote }}</p>
  </div>
</template>


<script>
import { computed } from 'vue'

const user = ref({
  name: 'John Doe',
  age: 30,
})

const birthYear = computed(() => {
  return new Date().getFullYear() - user.value.age
})

const canVote = computed(() => {
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

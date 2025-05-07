

<template>
  <div class="fullpart">
    <div class="datepart">
      <div class="datebox">
        <label>{{ formatted }}</label>
      </div>
    </div>
    <div class="container-fluid backgroundpart">
      <div class="contentcard">
        <h2 class="congratshead">Congratulations</h2>
        <div class="profile">
          <img
            src="https://randomuser.me/api/portraits/men/75.jpg"
            alt="Profile"
            class="profile-pic"
          />
          <h4 class="name">Kiran V</h4>
          <p class="college">
            Vishnu Institute of Computer Education and Technology,<br />
            Bhimavaram
          </p>
        </div>
        <img
          src="https://cdn-icons-png.flaticon.com/512/888/888879.png"
          alt="Gift"
          class="gift-img"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from 'vue'

// 1. Define a reactive "now" value (like useState)
const now = ref(new Date())

// 2. Create the "formatted" computed prop (like a React derived value)
const formatted = computed(() =>
  now.value.toLocaleString('en-GB', {
    weekday: 'long',
    day:     '2-digit',
    month:   'short',
    year:    'numeric',
    hour:    '2-digit',
    minute:  '2-digit',
    second:  '2-digit',
    hour12:  false
  })
)

// 3. On mount, start an interval that updates "now" every second (like useEffect)
let timer
onMounted(() => {
  timer = setInterval(() => {
    now.value = new Date()
  }, 1000)
})

// 4. On unmount, clear the interval (cleanup in useEffect)
onBeforeUnmount(() => {
  clearInterval(timer)
})
</script>

<style scoped>
/* (your existing CSS here) */
</style>

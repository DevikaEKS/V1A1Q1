
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

<script>
export default {
  name: 'CongratulationsCard',
  data() {
    return {
      now: new Date(),
      timer: null,
    };
  },
  computed: {
    formatted() {
      return this.now.toLocaleString('en-GB', {
        weekday: 'long',
        day:     '2-digit',
        month:   'short',
        year:    'numeric',
        hour:    '2-digit',
        minute:  '2-digit',
        second:  '2-digit',
        hour12:  false
      });
    }
  },
  mounted() {
    // update every second
    this.timer = setInterval(() => {
      this.now = new Date();
    }, 1000);
  },
  beforeUnmount() {
    clearInterval(this.timer);
  }
}
</script>

<style scoped></style>


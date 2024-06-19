<template>
  <form class="container">
 <input type="text" placeholder="First Name" required v-model="firstName">
 <input type="text" placeholder="Last Name" required v-model="lastName">
 <input type="text" placeholder="Gender" required v-model="gender" :class="{
  male: lowerCaseGender == 'male',
  female: lowerCaseGender == 'female'
 }">
 <textarea name="" id="" cols="30" rows="10"></textarea>
 <label output></label>
 <button @click.prevent="userInfo">Display</button>
</form>
</template>

<script>
 export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      firstName: '',
      lastName: '',
      gender: ''
    }
    
  },
  computed: {
    lowerCaseGender() {
      return this.gender.toLowerCase()
    }
  },
  methods: {
    userInfo() {
      document.querySelector('[output]').textContent =
      `
      First name: ${this.firstName}
      Last name: ${this.lastName}
      Gender: ${this.gender}
      `
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  display: grid;
  gap: .2rem;
  width: 30rem;
  margin-inline: auto;
  & input { 
    text-align: center;
  }
}
.male {
  border: 2px solid blue;
}
.female {
  border: 2px solid pink;
}
</style>

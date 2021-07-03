<template>
  <div class="logo">
    <img alt="Vue logo" src="../assets/logo.png">
    <p>
      {{ fullName }}
    </p>
    <p>
      {{ 'Age : ' + age }}
    </p>
    <h1>
      {{ fullName }}
    </h1>
    <button @click="callAlert(fullName)">
      Click me
    </button>
  </div>
</template>

<script>
export default {
  name: 'Logo',
  data () {
    return {
      firstname: 'Saman',
      lastname: 'Rashidi',
      age: 31
    }
  },
  computed: {
    fullName () {
      const output = this.firstname + ' ' + this.lastname
      return output
    }
  },
  methods: {
    callAlert (message) {
      alert(message)
    }
  }
}
</script>

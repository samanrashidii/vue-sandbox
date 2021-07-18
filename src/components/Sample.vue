<template>
  <div class="sample">
    <img alt="Vue logo" src="../assets/logo.png">
    <p>
      {{ 'Fullname : ' + fullName }}
    </p>
    <p>
      {{ 'Age : ' + age }}
    </p>
    <p v-if="age > 30">
      {{ firstname + ' is older than 30' }}
    </p>
    <p v-else>
      {{ firstname + ' is younger than 30' }}
    </p>
    <p>
      <strong>My favorite fruits : </strong>
      <ul>
        <li
          v-for="(fruit, index) in fruits"
          :key="index"
        >
          {{ fruit }}
        </li>
      </ul>
    </p>
    <button @click="changeAge(age)">
      Click me to increase age
    </button>
  </div>
</template>

<script>
export default {
  name: 'Sample',
  props: {
    firstname: {
      type: String,
      default: ''
    },
    lastname: {
      type: String,
      default: ''
    },
    age: {
      type: Number,
      default: 0
    },
    fruits: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    fullName () {
      const output = this.firstname + ' ' + this.lastname
      return output
    }
  },
  methods: {
    changeAge (age) {
      this.$emit('age', age)
    }
  }
}
</script>

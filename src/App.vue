<template>
  <TheHeader 
    :title="title"
  />
  <TheInformation />

</template>

<script>
import TheHeader from './components/Layout/TheHeader.vue'
import TheInformation from './components/Layout/TheInformation.vue'

export default {
  components: {
    TheHeader,
    TheInformation,
  },
  data() {
    return {
      title: 'Covid Safe Registration App',
      showRegistrationForm: false
    }
  },
  methods: {
    displayForm() {
      this.showRegistrationForm = true;
    }
  }
}
</script>

<style>
/* importing google font */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>

<template>
  <base-card>
      <form @submit.prevent="saveUserInput">
        <div class="mb-3">
          <label for="name" class="form-label">Full Name:</label>
          <input type="text" class="form-control" id="name" ref="name">
        </div>
        <div class="mb-3">
          <label for="email" class="form-label">Email address:</label>
          <input type="email" class="form-control" id="email" ref="email">
        </div>
        <div class="mb-3">
          <label for="phone" class="form-label">Phone Number:</label>
          <input type="number" class="form-control" id="phone" ref="phone">
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
      </form>
  </base-card>
    
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    saveUserInput() {
      const userName = this.$refs.name.value;
      const userEmail = this.$refs.email.value;
      const userPhone = this.$refs.phone.value;
      this.addUserToQue(userName, userEmail, userPhone)
    },
  },
  inject: ['addUserToQue']
}
</script>

<style scoped>

</style>
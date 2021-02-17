<template>
  <base-card>
      <h6>
        This is the covid vaccine registration app. Please register by clicking the button below and inputting your details. 
      </h6>

      <button 
        class="btn btn-primary"
        @click="setSelectedTab('register-user')"
      >Register</button>

      <button
        class="btn btn-secondary"
        @click="setSelectedTab('show-que')"
      >View Que</button>
  </base-card>

  <!-- show component based on which one is selected -->
  <component :is="selectedTab"></component>

</template>

<script>
import BaseCard from '../BaseComponents/BaseCard.vue'
import RegisterUserForm from '../CovidResources/RegisterUserForm.vue'
import UserQue from '../CovidResources/UserQue.vue'

export default {
  components: {
      'register-user': RegisterUserForm,
      'show-que' : UserQue,
    BaseCard
  },
  data() {
    return {
      selectedTab: '',
      userList: [
        {
          id: 'first-user',
          name: 'Jason Hoffman',
          phone: 123456789,
          email: 'jason@mail.com'
        }
      ],
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addUserToQue(name, email, phone) {
      const newUser = {
        id: new Date().toISOString(),
        name: name,
        email: email,
        phone: phone
      }
      this.userList.unshift(newUser);
      this.selectedTab = 'show-que'
    }
  },
  provide() {
    return {
      addUserToQue: this.addUserToQue,
      users: this.userList
    }
  }
}
</script>

<style scoped>
p {
  margin: 0;
}

button {
  margin: 0.5rem;
}
</style>
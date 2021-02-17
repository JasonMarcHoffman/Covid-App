<template>
  <base-card>
    <div 
      v-for="user in users"
      :key="user"
    >
      {{ user.name}} | {{ user.phone }} | {{ user.email }}
    </div>
  </base-card>
  <base-card>
    Number of people in the que..
  </base-card>
</template>

<script>
export default {
  inject: ['users'],
}
</script>

<style>
  
</style>
<script setup>
import UserForm from "@/components/UserForm.vue"

function login(user){
// api request
}
</script>

<template>
    <div>
      <!-- Login page -->
      <UserForm formType="signin" @submit="login"/>
    </div>
</template>

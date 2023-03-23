<script setup>
// HomeView.vue
import UserForm from "@/components/userForm.vue"


function login(user){
    // api request
}
   </script> 

<template>
    <div>
        <!-- Sign up page -->
        <UserForm formType="signin" @submit="login"/>
    </div>
</template>

<style lang="scss" scoped>

</style>
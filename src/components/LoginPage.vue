<template>
    <img class="logo" src="../assets/resto-logo.jpg" alt="Logo" />
    <h1>Login</h1>
    <div class="login">
        <input v-model="email" type="text" placeholder="Enter Email" />
        <input v-model="password" type="password" placeholder="Enter Password" />
        <button>Login</button>
        <p>
            <router-link to="/sign-up">Sign Up</router-link>
        </p>
    </div>
</template>

<script>
    export default {
        name: 'LoginPage'
    }
</script>
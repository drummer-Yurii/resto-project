<template>
    <img class="logo" src="../assets/resto-logo.jpg" alt="Logo" />
    <h1>Sign Up</h1>
    <div class="register">
        <input v-model="name" type="text" placeholder="Enter Name" />
        <input v-model="email" type="text" placeholder="Enter Email" />
        <input v-model="password" type="password" placeholder="Enter Password" />
        <button @click="signUp">Sign Up</button>
        <p>
            <router-link to="/login-page">Login</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'SignUp',
    data() {
        return {
            name: '',
            email: '',
            password: ''
        }
    },

    methods: {
        async signUp() {
            let result = await axios.post("http://localhost:3000/users", {
                email: this.email,
                name: this.name,
                password: this.password
            });

            console.warn(result);

            if (result.status == 201) {
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({name: 'HomePage'})
            }
        }
    },

    mounted() {
        let user = localStorage.getItem('user-info');

        if (user) {
            this.$router.push({ name: 'HomePage' })
        }
    },
}
</script>

<style>

</style>
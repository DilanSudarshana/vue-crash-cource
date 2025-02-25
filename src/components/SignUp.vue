<template>
    <h1>Sign Up</h1>
    <div class="container">
        <div class="row">
            <input type="text" v-model="name" placeholder="Enter Name">
        </div>
        <div class="row">
            <input type="email" v-model="email" placeholder="Enter Email">
        </div>
        <div class="row">
            <input type="password" v-model="password" placeholder="Enter Password">
        </div>
        <div>
            <button v-on:click="signUp" style="margin-top: 20px;">Sign Up</button>
        </div>
        <p>
            <router-link to="/login">Go to Login</router-link>
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
                name: this.name,
                password: this.password,
                email: this.email
            });
            if (result.status == 201) {
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({ name: 'Home' })
            }
        }
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (user) {
            this.$router.push({ name: 'Home' })
        }
    }

}

</script>

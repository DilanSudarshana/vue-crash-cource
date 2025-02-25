<template>
    <h1>Login Here</h1>
    <div class="container">
        <div class="row">
            <input type="email" v-model="email" placeholder="Enter Email">
        </div>
        <div class="row">
            <input type="password" v-model="password" placeholder="Enter Password">
        </div>
        <div>
            <button v-on:click="login" style="margin-top: 20px;">Login</button>
        </div>
        <p>
            <router-link to="/sign-up">Go to Sign Up</router-link>
        </p>
    </div>

</template>

<script>
import axios from 'axios';

export default {
    name: 'Login',

    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        async login() {
            let result = await axios.get(
                `http://localhost:3000/users?email=${this.email}&password=${this.password}`
            )

            if (result.status == 200 && result.data.length > 0) {
                localStorage.setItem("user-info", JSON.stringify(result.data[0]))
                this.$router.push({ name: 'Home' })
            } else {
                alert('error login')
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
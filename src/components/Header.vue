<template>
    <div class="nav">
        <a href="">Home | </a>
        <a href="">Add Resturant | </a>
        <a href="">Update Resturant | </a>
        <a v-on:click="logOut">Logout</a>
    </div>

</template>

<script>
export default {
    name: 'Header',

    methods: {
        logOut() {
            localStorage.clear();
            this.$router.push({name:'Login'})
        }
    }
}
</script>

<style></style>
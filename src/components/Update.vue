<template>
    <Header></Header>
    <h1>Wellcome to Update Resturant page</h1>
</template>


<script>
import Header from './Header.vue';
export default {

    name: 'Update',

    components: {
        Header
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'SignUp' })
        }
    }
}
</script>

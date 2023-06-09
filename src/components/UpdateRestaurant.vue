<template>
    <HeaderPage />
    <h1>Wellcome to UpdateRestaurant page</h1>
</template>

<script>
import HeaderPage from './HeaderPage.vue';
export default {
    name: 'UpdateRestaurant',

    components: {
        HeaderPage
    },

    mounted() {
        let user = localStorage.getItem('user-info');

        if (!user) {
            this.$router.push({ name: 'SignUp' })
        }
    },
}
</script>

<style lang="scss" scoped></style>
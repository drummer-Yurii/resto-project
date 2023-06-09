<template>
    <h1>Wellcome to Home page</h1>
</template>

<script>
export default {
    name: 'HomePage',

    mounted() {
        let user = localStorage.getItem('user-info');

        if (!user) {
            this.$router.push({ name: 'SignUp' })
        }
    },
}
</script>

<style lang="scss" scoped></style>
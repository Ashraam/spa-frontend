<template>
    <form @submit.prevent="login">
        <input type="email" placeholder="Email address" v-model="form.email" />
        <input type="password" placeholder="Password" v-model="form.password" />
        <button type="submit">Login</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            form: {
                email: '',
                password: ''
            }
        }
    },

    methods: {
        login() {
            this.$store.dispatch('login', this.form);
        }
    }
}
</script>
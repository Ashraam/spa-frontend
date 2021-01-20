<template>
    <div class="home">
        <div v-if="isAuthenticated">
            <h1>Welcome {{ user.name }}</h1>
            <button @click="testApi">Test API</button>
        </div>

        <div v-else>
            <h2>You have to login first</h2>
        </div>
    </div>
</template>

<script>
import axios from '@/api/axios'

export default {
    name: 'Home',

    methods: {
        async testApi() {
            const res = await axios.get('api/test');

            console.log(res.data);
        }
    },

    computed: {
        isAuthenticated() {
            return this.$store.getters.isAuthenticated;
        },

        user() {
            return this.$store.getters.user;
        }
    }
}
</script>

<template>
    <div id="register">
        <h1>Register</h1>

        <div><input type="email" name="email" placeholder="email" v-model="email" /></div>
        <div><input type="password" name="password" placeholder="password" v-model="password" /></div>
        <div><button @click="Register">Register</button></div>
    </div>
</template>

<script>
import AuthenticationService from '../services/AuthenticationService'

export default {
    data() {
        return{
            email: '',
            password: ''
        }
    },
    methods: {
        Register: async function() {
            const response = await AuthenticationService.register({
                email: this.email,
                password: this.password
            })
            console.log(response.data);
        }
    }
}
</script>

<style scoped>

</style>
<template>
    <div>
        <h1>Home</h1>
        <router-link to="/test">Take me to test</router-link>
        <div>
            <button @click="getValue">Trigger Endpoint</button>
            <p v-if="response">{{ response.data }}</p>
        </div>
    </div>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";

const response = ref();

const getValue = async () => {
    try {
        response.value = await axios.get("/api/test-me");
    } catch (error) {
        console.log(error);
    }
};
</script>

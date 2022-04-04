<template>
    <div>
        <form @submit.prevent="handleSubmit">
            <input
                type="text"
                v-model="user.username"
                name="username"
                id="username"
                placeholder="username"
            />
            <input
                type="password"
                v-model="user.password"
                name="password"
                id="password"
                placeholder="********"
            />
            <input type="submit" name="valider" id="co-button" />
        </form>
    </div>
</template>
<script setup lang="ts">
import { ref } from "@vue/reactivity";
import fetchLogin from "../plugins/fetch";

const user = ref({
    username: "",
    password: "",
});

const handleSubmit = () => {
    fetchLogin(user.value);
};
</script>

<style>
form {
    display: flex;
    flex-direction: column;
}
form input,
textarea,
h1 {
    width: 50%;
    margin: auto;
    padding: 10px;
    border-radius: 5px;
    outline: none;
    border-color: hsla(160, 100%, 37%, 1);
    color: white;
    background-color: #181818;
    margin-top: 2%;
}

#co-button {
    margin-top: 2%;
    width: 20%;
    color: hsla(160, 100%, 37%, 1);
    padding: 10px;
    cursor: pointer;
    background-color: #000000;
}
#co-button:hover {
    background-color: #181818;
}
</style>
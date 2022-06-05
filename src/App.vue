<template>
  <h1>Login</h1>
  <br />
  <div>
    <form
      @submit.prevent="signInHandler()"
      class="form-group text-center card container"
      style="width: 30%; padding: 0.9rem"
    >
      <div class="form-floating mb-3">
        <input
          class="form-control"
          type="text"
          placeholder="Username"
          v-model="userName"
        />
        <label>Username</label>
      </div>
      <div class="form-floating">
        <input
          class="form-control"
          type="password"
          placeholder="Password"
          v-model="password"
        />
        <label>Password</label>
      </div>
      <button class="btn btn-primary btn-lg mt-4">Sign In</button>
    </form>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",

  setup() {
    let userName = ref("");
    let password = ref("");

    function signInHandler() {
      console.log(userName.value, password.value);
      userName.value = "";
      password.value = "";
    }

    return {
      userName,
      password,
      signInHandler,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

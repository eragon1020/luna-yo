<template>
  <div class="2xl:w-60 flex flex-col items-center" name="container">
    <div class="relative w-full">
      <h1 class="text-[#fff] text-4xl absolute top-24 left-24 sm:text-7xl sm:top-52 sm:left-40">Welcome Back</h1>
      <p class="text-[#ffffff] text-xl absolute top-32 left-28 sm:text-4xl sm:top-72 sm:left-48">Nice to see you again!</p>
    </div>
    <div class="sm:ml-96 sm:w-8/12 sm:rounded-md sm:h-full">
      <div class="bg-[#fff] sm:ml-96 sm:w-8/12 sm:rounded-3xl sm:h-full p-8">
        <div class="text-center sm:text-left">
          <img src="../assets/image.jpg" class="m-auto sm:mr-48" />
          <h1 class="my-10 text-4xl">Login</h1>
        </div>
        <form name="login-form" class="flex flex-col items-center">
          <div class="w-full sm:w-8/12">
            <label for="username" class="block ml-12 sm:ml-0">Username</label>
            <div class="relative">
              <input type="text" id="username" v-model="input.username" class="p-2 rounded-lg my-4 w-full shadow-lg shadow-[#a9d2fa]" />
              <i class=""></i>
            </div>
          </div>
          <div class="w-full sm:w-8/12">
            <label for="password" class="block ml-12 sm:ml-0">Password</label>
            <div class="relative">
              <input :type="showPassword ? 'text' : 'password'" id="password" v-model="input.password" class="p-2 rounded-lg my-4 w-full shadow-lg shadow-[#a9d2fa]" />
              <i @click="togglePasswordVisibility" class="cursor-pointer"></i>
            </div>
            <a href="#" class="block ml-12 sm:ml-0">Forgot password?</a>
          </div>
          <div class="w-full sm:w-8/12 mt-4">
            <div class="flex items-start ml-12 sm:ml-0">
              <input type="checkbox" v-model="condiciones" id="condiciones" name="condiciones" />
              <label for="condiciones" class="ml-3">I acknowledge and agree to comply with <br /> the stated policies and terms</label>
            </div>
          </div>
          <div class="w-full sm:w-8/12 mt-4">
            <div class="flex items-center ml-12 sm:ml-0">
              <input type="checkbox" name="remember" class="mr-3" />
              <label for="remember">Remember me</label>
            </div>
          </div>
          <button type="submit" @click.prevent="login" :disabled="isButtonDisabled" class="bg-[#127dd6] w-full h-10 rounded-xl mt-5 cursor-pointer sm:mb-12">Start</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginView",
  data() {
    return {
      input: {
        username: "",
        password: "",
      },
      condiciones: false,
      showPassword: false,
    };
  },
  methods: {
    login() {
      if (this.input.username !== "" && this.input.password !== "") {
        console.log("authenticated");
      } else {
        console.log("Username and Password can not be empty");
      }
    },
    togglePasswordVisibility() {
      this.showPassword = !this.showPassword;
    },
  },
  computed: {
    isButtonDisabled() {
      return !this.condiciones;
    },
  },
};
</script>

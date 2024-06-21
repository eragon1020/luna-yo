<template>
  <div class="2xl:w-60 " name="container">
    <div class="static ">
        <h1 class="text-[#fff] text-4xl absolute  top-24 left-24 sm:text-7xl sm:top-52 sm:left-40">Welcome Back</h1>
        <p class="text-[#ffffff] text-xl  absolute top-32 left-28 sm:text-4xl sm:top-72 sm:left-48">Nice to see you again!</p>
 
      </div>
    <div class="sm:ml-96 sm:w-8/12 sm:rounded-md sm:h-full">
      <div class="bg-[#fff]  sm:ml-96 sm:w-8/12 sm:rounded-3xl sm:h-full">
        <div class=" ">
          <img src="../assets/image.jpg" class="m-auto sm:mr-48" />

          <h1 class="my-10 text-4xl text-center sm:mr-20">Login</h1>
        </div>
        <form name="login-form" class="">
          <div class="ml-12 sm:ml-24">
            <label for="username" class="">Username</label>
            <div class="relative">
              <input
                type="text"
                id="username"
                v-model="input.username"
                class="p-2 rounded-lg m-auto my-4 w-80 shadow-lg shadow-[#a9d2fa]"
              />
              <i class=""></i>
            </div>
          </div>
          <div class="ml-12 sm:ml-24">
            <label for="password" class="">Password</label>
            <div class="relative">
              <input
                :type="showPassword ? 'text' : 'password'"
                id="password"
                v-model="input.password"
                class="p-2 rounded-lg m-auto my-4 w-80 shadow-lg shadow-[#a9d2fa]"
              />
              <i @click="togglePasswordVisibility"></i>
            </div>
            <a href="#" class="">Forgot password?</a>
          </div>
          <div class=" ml-8 sm:ml-24">
            <input
              type="checkbox"
              v-model="condiciones"
              id="condiciones"
              name="condiciones"
              class=""
            />
            <label for="condiciones" class="ml-3" 
              >I acknowledge and agree to comply with <br/>  thestated policies and 
              terms</label
            >
          </div>
          <div class="ml-8 sm:ml-24">
            <input type="checkbox" name="remember" class="mr-3" />
            <label for="remember" class="mr-2">Remember me</label>
          </div>
          <button
            type="submit"
            @click.prevent="login"
            :disabled="isButtonDisabled"
            class="bg-[#127dd6] w-96 h-10 rounded-xl ml-5 mt-5 cursor-pointer sm:mb-12 sm:ml-24 sm:w-80"
          >
            Start
          </button>
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

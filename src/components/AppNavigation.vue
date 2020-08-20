<template>
  <div class="AppNavigation">
    <nav class="nav">
      <div class="nav_item">
        <img src="../assets/images/logo.svg" alt="logo" />
        <router-link to="/">Features</router-link>
        <router-link to="/">Pricing</router-link>
        <router-link to="/">Resources</router-link>
      </div>

      <div class="auth">
        <button class="login">Login</button>
        <button class="signup">Sign Up</button>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppNavigation"
};
</script>

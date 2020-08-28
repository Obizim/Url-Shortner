<template>
  <div class="AppNavigation">
    <nav class="nav">
        <img src="../assets/images/logo.svg" alt="logo" />

          <div v-bind:class="{ openNav: isActive }" class="nav_item">
            <div class="links">
          <router-link to="/">Features</router-link>
          <router-link to="/">Pricing</router-link>
          <router-link to="/">Resources</router-link>
            </div>
            
      <div class="auth">
        <button class="login">Login</button>
        <button class="signup">Sign Up</button>
      </div>
     </div>

      <div @click="openNav" v-bind:class="{ openNav: isActive }" class="menu">
        <img
          src="../assets/images/icon-hamburger.svg"
          alt="hamburger-menu"
          id="burger"
        />
        <img
          src="../assets/images/icon-close.svg"
          alt="close-menu"
          id="close-menu"
        />
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "AppNavigation",
  data() {
    return {
      isActive: false
    };
  },
  methods: {
    openNav() {
      if (!this.isActive) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
    }
  }
};
</script>

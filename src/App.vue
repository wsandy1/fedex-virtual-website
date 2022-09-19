<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="header-content">
      <RouterLink to="/"><img class="logo" src="./assets/images/logo-white.png"/></RouterLink>
      <nav>
        <RouterLink class="nav-link" to="/">Home</RouterLink>
        <RouterLink class="nav-link" to="/fleet">Fleet</RouterLink>
        <RouterLink class="nav-link" to="/team">Team</RouterLink>
        <a class="nav-link" href="https://vamsys.io/register/fdxvirtual">Join</a>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<style scoped>

header {
  background-color: var(--brand-purple);
  font-family: "FuturaBold";
  user-select: none;
}

.header-content {
  max-width: 60%;
  margin: 0 auto;
  padding: 20px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  pointer-events: none;
  max-height: 60px;
}

.nav-link {
  color: var(--brand-white);
  text-decoration: none;
  margin-left: 20px;
  font-size: 18px;
}

.router-link-active {
  color: var(--brand-orange);
}

</style>

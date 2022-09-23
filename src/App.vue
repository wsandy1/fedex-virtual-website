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
        <a class="nav-link" href="https://vamsys.io/register/fdxvirtual">Join</a>
      </nav>
    </div>
  </header>
  <RouterView />
  <footer>
    <p>&copy; &lt;Fedex Virtual&gt; 2022. Site made with <span class="heart">&lt;3</span> by <a href="https://github.com/wsandy1">Will S</a>.</p>
  </footer>
</template>

<style scoped>

header {
  background-color: var(--brand-purple);
  font-family: "FuturaBold";
  user-select: none;
}

.header-content {
  position: relative;
  max-width: 60%;
  margin: 0 auto;
  padding: 20px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

@media screen and (max-width: 1500px) {
  .header-content {
    max-width: 80%;
  }
}

@media screen and (max-width: 600px) {
  .header-content {
    max-width: 100%;
  }
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

footer {
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--brand-purple);
  color: var(--brand-white);
  font-family: "Roboto";
}

footer a {
  text-decoration: none;
  color: var(--brand-white);
  font-weight: bold;
}

.heart {
  color: red;
}

</style>

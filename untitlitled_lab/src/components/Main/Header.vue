<template>
  <header>
    <nav class="navbar-expand-lg">
      <div class="container">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 menu">
          <li class="nav-item">
            <router-link style="padding: 10px 40px" class="nav-link" :to="{name: 'Main'}">Главная</router-link>
          </li>

          <li class="nav-item">
            <router-link v-if="sign_in" style="padding: 10px 40px" class="nav-link" :to="{name: 'Login'}">Войти</router-link>
            <router-link v-else style="padding: 10px 40px" class="nav-link" :to="{name: 'Login'}">Аккаунт</router-link>
          </li>

          <li>
            <a>Пиво в социальных сетях</a>
            <ul class="submenu">
              <li><a target="_blank" href="https://vk.com/chronos386">VK</a></li>
              <li><a target="_blank" href="https://twitter.com/Chronos389">Twitter</a></li>
              <li><a target="_blank" href="https://www.instagram.com/chronos386/">Instagram</a></li>
              <li><a target="_blank" href="https://www.facebook.com/chronos386">Facebook</a></li>
            </ul>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
import VueCookies from "vue-cookie";

export default {
  name: "Header",
  data() {
    return {
      sign_in: VueCookies.get("api_key") === null
    }
  }
}
</script>

<style scoped>
header {
  background-color: rgb(121, 24, 24);
}

header .container {
  margin: 0 auto;
  padding: 0 15px;
  max-width: 1200px;
}

nav ul li {
  position: relative;
}

nav ul li a {
  color: white;
  padding: 10px 20px;
  display: inline-block;
  text-decoration: none;
}

nav ul li a:hover {
  background-color: rgb(166, 114, 31);
}

nav ul ul {
  top: 100%;
  display: none;
  position: absolute;
  z-index: 1;
}

nav ul li:hover ul {
  display: block;
}

.menu {
  display: flex;
  align-items: center;
}

.menu, .submenu {
  color: white;
  list-style: none;
  background-color: rgb(121, 24, 24);
}
</style>
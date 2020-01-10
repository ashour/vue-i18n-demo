<template>
  <div class="nav">
    <div class="nav__start">
      <img alt="Vue logo" src="../assets/logo-circle-sm.png" />

      <router-link to="/">{{ $t("nav.home") }}</router-link>
      <router-link to="/about">{{ $t("nav.about") }}</router-link>
    </div>

    <div class="nav__end">
      <LocaleSwitcher />
    </div>
  </div>
</template>

<script>
import LocaleSwitcher from "@/components/LocaleSwitcher"

export default {
  components: { LocaleSwitcher }
}
</script>

<style scoped>
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: left;
  padding: 1rem;
  color: #fff;
  background-color: #3d536a;
}

.nav__start,
.nav__end {
  display: flex;
  align-items: center;
}

.nav img {
  margin-right: 1rem;
}

.nav a {
  margin-right: 1.5rem;
  font-weight: bold;
  color: #fff;
  text-decoration: none;
}
</style>

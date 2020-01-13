<template>
  <div id="app">
    <div v-if="isLoading">Loading...</div>
    <div v-else>
      <Nav v-on:localeChange="loadLocaleMessages" />

      <div class="container">
        <router-view />
      </div>

      <Footer />
    </div>
  </div>
</template>

<script>
import Nav from "@/components/Nav"
import Footer from "@/components/Footer"
import {
  setDocumentDirectionPerLocale,
  setDocumentTitle,
  setDocumentLang
} from "@/util/i18n/document"
import { loadLocaleMessagesAsync } from "@/i18n"
export default {
  data: () => ({
    isLoading: true
  }),
  mounted() {
    this.loadLocaleMessages(this.$i18n.locale)
  },
  methods: {
    loadLocaleMessages(locale) {
      this.isLoading = true

      loadLocaleMessagesAsync(locale).then(() => {
        setDocumentLang(locale)

        setDocumentDirectionPerLocale(locale)

        setDocumentTitle(this.$t("app.title"))

        this.isLoading = false
      })
    }
  },
  components: { Nav, Footer }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#app .container {
  padding: 1rem;
}
</style>

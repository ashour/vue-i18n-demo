<template>
  <div class="locale-switcher">
    <select :value="$i18n.locale" @change.prevent="$emit('change', $event.target.value)">
      <option :value="locale.code" v-for="locale in locales" :key="locale.code">{{locale.name}}</option>
    </select>
  </div>
</template>

<script>
import { getSupportedLocales } from "@/util/i18n/supported-locales"
import { loadLocaleMessagesAsync } from "@/i18n"

export default {
  data: () => ({ locales: getSupportedLocales() })
}
</script>
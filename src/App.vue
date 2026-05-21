<template>
  <div id="app">
    <router-view />
    <theme-picker />
  </div>
</template>

<template>
  <div id="app">
    <router-view />
    <AiAssistant />
  </div>
</template>

<script>
// 引入刚才写的组件
import AiAssistant from '@/components/AiAssistant'

export default  {
  name:  'App',
  components: {
    AiAssistant
  },
  metaInfo() {
      return {
          title: this.$store.state.settings.dynamicTitle && this.$store.state.settings.title,
          titleTemplate: title => {
              return title ? `${title} - ${process.env.VUE_APP_TITLE}` : process.env.VUE_APP_TITLE
          }
      }
  }
}
</script>

<script>
import ThemePicker from "@/components/ThemePicker"

export default {
  name: "App",
  components: { ThemePicker }
}
</script>
<style scoped>
#app .theme-picker {
  display: none;
}
</style>

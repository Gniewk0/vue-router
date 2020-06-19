<template>
  <div id="app">
    <div id="nav">
      <TheNavigation></TheNavigation>
    </div>
    <router-view :key="$route.path" />
  </div>
</template>

<script>
import TheNavigation from "@/components/TheNavigation"
export default {
  components: {
    TheNavigation
  }
}
</script>
<style>

</style>

<template>
  <div id="app">
    <VtHeader />
    <main>
      <router-view/>
    </main>
    <VtFooter />
  </div>
</template>

<script>
import VtHeader from '@layout/VtHeader'
import VtFooter from '@layout/VtFooter'
export default {
  name: 'App',
  components: {
    VtHeader,
    VtFooter
  }
}
</script>

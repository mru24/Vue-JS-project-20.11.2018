<template>
  <div class="container">
    <router-link :to="'/about'">
      <h1>hi</h1>
      <h3>my name is Val</h3>
    </router-link>
  </div>
</template>

<script>

export default {
  data () {
    return {

    }
  }
}
</script>

<style lang="sass" scoped>
h1
  font-size: 80px
.container
  background: #4b4b4b
  color: white

</style>

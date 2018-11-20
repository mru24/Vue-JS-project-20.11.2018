<template>
  <div id="app">
    <transition mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<style lang="sass">
*
  margin: 0
  padding: 0
  box-sizing: border-box

a, a:active, a:visited
  text-decoration: none
  color: inherit

ul
  list-style: none

body, html
 font-family: sans-serif
 background: #1f1f1f

#app
  height: 100vh
  overflow: hidden

.container
  height: 100%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.v-enter-active, .v-leave-active
  transition: transform .5s
.v-enter
  transform: translateY(100%)
.v-leave-to
  transform: translateY(-100%)
</style>

<template>

  <div class="container">
    <router-link :to="'/contact'">
      <h1>MY WORK</h1>
    </router-link>
    <!-- <input type="text" v-model="query"> -->
    <div class="nav">
      <button v-for="(button, index) in buttons" :key="index" @click="query=button.value">{{ button.name }}</button>
    </div>
    <div class="content">
      <transition-group
        tag= "ul"
        name= "box"
        mode="out-in"
        >
        <li class="box" v-for="(item, index) in computedList" :key="index">
          <p class="title">{{ item.title }}</p>
          <p class="content">{{ item.content }}</p>
        </li>
      </transition-group>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      buttons: [
        { name: 'all', value: '', active: false},
        { name: 'Responsive Design', value: 'resp', active: false},
        { name: 'Java Script', value: 'js', active: false},
        { name: 'PHP', value: 'php', active: false}
      ],
      query: '',
      list: [
        { title: 'responsive design', content: '', cat: 'resp'},
        { title: 'java script', content: '', cat: 'js'},
        { title: 'responsive design', content: '', cat: 'resp'},
        { title: 'java script', content: '', cat: 'js'},
        { title: 'php', content: '', cat: 'php'},
        { title: 'responsive design', content: '', cat: 'resp'}
      ]
    }
  },
  computed: {
    computedList: function () {
      var vm = this
      return this.list.filter(function (item) {
        return item.cat.indexOf(vm.query) !== -1
      })
    }
  }
}

</script>

<style lang="sass" scoped>

.container
  background: #490f0f
  color: white
  display: block
  padding-top: 10%
  h1
    text-align: center

.nav
  width: 80%
  margin: 40px auto
  display: flex
  flex-direction: row
  justify-content: center
  button
    padding: 9px 20px
    margin: 8px
    text-transform: capitalize
    background: #dd7e0f
    color: white
    border: none
    border-radius: 4px
    cursor: pointer
    transition: .5s
    &:hover
      background: #cd5c00
      box-shadow: 0 0 15px #444
    &:focus
      background: green

.content
  width: 80%
  margin: 40px auto
  ul
    transition: .5s
    display: flex
    flex-direction: row
    flex-wrap: wrap
    justify-content: center
    .box
      $width: 12vw
      width: $width
      min-width: 150px
      height: $width + 2
      min-height: 170px
      margin: 5px
      padding: 4px
      background: #eee
      border: 1px solid #666
      transition: .5s
      .title
        color: black
        font-size: 18px
        text-align: center
        text-transform: capitalize

.box-enter, .box-leave-to
  opacity: 0
  transform: translateY(30px)
.box-leave-active
  position: absolute

</style>

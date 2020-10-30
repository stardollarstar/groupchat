<template>
  <div id="app">
    <Side style="min-height: 100vh;"/>
    <Chat style="min-height: 100vh;"/>
  </div>
</template>


<script>
import Side from './components/Sidebar'
import Chat from './components/Chat'

export default {
  name: 'App',
  components: {
    Side,
    Chat
  }
}
</script>

<style>
  #app {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
  }
</style>
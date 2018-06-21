<template>
  <div id="app">
    <div>
      <Porfolio v-bind="users"></Porfolio>
    </div>
    <router-view/>
  </div>
</template>

<script>
import Porfolio from './components/Porfolio/Porfolio'
export default {
  name: 'App',
  components: {
    Porfolio
  },
  data () {
    return {
      users: [{
                  id: '1',
                  email: 'khale@success.com',
                  fullName: 'Kha Le',
                  password: '123',
                  avatar: 'avatar.png'
                }],
    };
  }
}
</script>
<style src="./main.scss"></style>

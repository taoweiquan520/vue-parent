<template>
  <div id="container">
    <div class="wrap">
      <div class="menu">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <!-- <li><router-link to="/demo1">子应用list</router-link></li>
          <li><router-link to="/demo1">子应用about</router-link></li> -->

          <li><a @click="goto('vue app', '/demo1')">子应用list</a></li>
        </ul>
        
      </div>
      <div class="content">
        <router-view></router-view>
        <div v-if="loading">loading</div>
        <div class="appContainer" v-html="content">content</div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  props: {
    loading: Boolean,
    content: String,
  },
  methods: {
    goto(title, href) {
      window.history.pushState({}, title, href);
    }
	}
}
</script>

<style scoped>
#container {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
li {
  list-style: none;
}
.wrap {
  
}
.wrap .menu {
    width: 200px;
    height: 100%;
    border-right: 1px solid #ccc;
  }
.wrap .content {
  margin-left: 200px;
}
</style>

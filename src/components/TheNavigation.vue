<template>
    <nav id="nav">
        <ul class="nav-links">
            <li class="links">
                <router-link to="/">
                    Home
                </router-link>
            </li>
            <li v-for="destination in destinations"
            :key="destination.name"
            class="links">
                <router-link :to="{name: 'DestinationDetails', params: {slug: destination.slug}}">
                    {{destination.name}}
                </router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
import store from "../store.js"
export default {
    data(){
        return {
             destinations: store.destinations
        } 
    },
}
</script>

<style  scoped>
    #nav {
        display: flex;
        justify-content: center;
    }
    #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 10px;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
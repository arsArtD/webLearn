<template>
  <div id="app">
    <!--<p>
      <router-link to="/home">Go to home</router-link>
      <router-link to="/city">Go to city</router-link>
    </p>-->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss">
  @import './style/common';
	.router-fade-enter-active, .router-fade-leave-active {
	  	transition: opacity .3s;
	}
	.router-fade-enter, .router-fade-leave-active {
	  	opacity: 0;
	}
</style>


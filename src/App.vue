<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ message }}</h1>
    <!-- eslint-disable-next-line -->
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis repellat quaerat, ut, incidunt culpa repudiandae accusamus dolorem obcaecati error corrupti vero, eveniet qui explicabo laborum possimus. Maiores minus molestias provident!</p>
    <ul>
      <li
        v-for="(item, index) in items"
        :key="index">{{ item }}</li>
    </ul>
    <component-with-store/>
  </div>
</template>

<script>
import ComponentWithStore from '@/components/ComponentWithStore';

export default {
  name: 'App',
  components: {
    ComponentWithStore,
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      message: 'Hello Vuejs',
      secret: process.env.VUE_APP_SECRET,
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $color-blue;
  margin-top: 60px;
  padding: 0 30px;
  @include breakpoint(768px) {
    font-size: 20px;
  }
}
</style>

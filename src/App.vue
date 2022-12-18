<template>
  <div id="app" >
    <header>
      <header-component/>
    </header>
    <div class="ProductPanel">
      <card-panel/>
    </div>
    <div class=footer>
      <footer-compo/>
    </div>
  </div>
</template>

<script>

import cardPanel from "@/components/cardPanel.vue";
import headerComponent from "@/components/MainLayout/headerComponent.vue";
import footerCompo from "@/components/MainLayout/footerCompo.vue";
export default {
  name: 'App',
  components: {
    footerCompo,
    cardPanel,
    headerComponent,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.footer{
  bottom: 0;
  width: 100%;
  height: 45vh;
  display: flex;
  align-items: end;
  /* Height of the footer*/

}
</style>

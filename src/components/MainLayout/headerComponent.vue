<template>
<div class="headerContainer">
  <h2 class="headerTitle"> Minista </h2>
  <div class="headerBtns">
    <button class="btn" style="width: 50px;height: 50px">
      <b-icon class="icon" icon="bell" font-scale="2"></b-icon>
    </button>
    <img class="headerImg" :src="haderImg" width="50" height="50">
  </div>
</div>
</template>

<script>

export default {
  name: "headerComponent",
  data(){
    return{
      haderImg:'https://img.freepik.com/free-photo/close-up-portrait-wonderful-child-with-shiny-brown-eyes-looking-with-interest-enthusiastic-little-girl-vintage-straw-hat-decorated-with-ribbon-posing-during-game-park_197531-3960.jpg?w=2000',
    }
  }
}
</script>

<style lang="scss" scoped>
  .headerContainer{
    display: flex;
    justify-content: space-between;
    margin: 20px;
    .headerBtns{
      display: flex;
      align-items: center;
      .headerImg{
        padding-left: 5px;
        border-radius: 50%;
      }
    }
    .headerTitle{
      padding-left: 20px;
    }
  }

</style>
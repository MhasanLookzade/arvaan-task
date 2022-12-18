<template>
  <div class="row footer">
    <div class="col footerContainer"
        v-for="(item,index) in items"
        :key="index">
      <button
          class="footerBtn btn" id="footerBtn" >
        <b-icon :icon="item.name" class="icon" font-scale="1.5"></b-icon>
        <p>{{ item.title }}</p>
      </button>
    </div>

  </div>

</template>

<script>
export default {
  name: "footerCompo",
  data() {
    return {
      items: [
        {name: 'house-fill', to: '/index' ,title:'Home'},
        {name: 'gear-fill',title:'Settings'},{name: 'calendar-fill',title:'Calendar', to: '/index'},
        {name: 'book-fill',title:'Bookings'},
        {name: 'cart-fill', to: '/index',title:'Shop'},
        {name: 'bag-check-fill',title:'Order'},
        {name: 'bookmark-fill',title:'Bookmark'},
        {name: 'heart-fill',title:'Wishlist'},
        {name: 'person-fill',title:'Profile'},
      ]
    }
  },
  methods: {
    goTo(link,index) {
      console.log(link)
      console.log(index)
      const footer = document.getElementById('footerBtn')
      console.log(footer)
      footer.style.color="red"
    },
  }
}
</script>

<style lang="scss" scoped>
.footer {

  .footerContainer{
    :focus{
      color: purple;
    }

  }
  .footerBtn {
    color: grey;
    height: 60px;
    border-bottom: 1px purple;
    .icon {
    }
  }
}
</style>
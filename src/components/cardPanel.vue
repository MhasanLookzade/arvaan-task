<template>
  <div class="headerContainer">
    <div class="header">
      <p class="headerTitle">My Bookings</p>
      <div class="icons">
        <button class="headerBtn btn">
          <b-icon class="icon" icon="search" font-scale="1"></b-icon>
        </button>
        <button class="headerBtn btn">
          <b-icon class="icon" icon="three-dots" font-scale="2"></b-icon>
        </button>
      </div>
    </div>
    <main>
      <input id="tab1" type="radio" name="tabs">
      <label for="tab1">Upcoming</label>

      <input id="tab2" type="radio" name="tabs" checked>
      <label for="tab2">Completed</label>

      <input id="tab3" type="radio" name="tabs">
      <label for="tab3">Cancelled</label>

      <input id="tab4" type="radio" name="tabs">
      <label for="tab4">History</label>


      <section id="content1">
        <p>
          Bacon ipsum dolor sit amet beef venison beef ribs kielbasa. Sausage pig leberkas, t-bone sirloin shoulder
          bresaola. Frankfurter rump porchetta ham. Pork belly prosciutto brisket meatloaf short ribs.
        </p>
        <p>
          Brisket meatball turkey short loin boudin leberkas meatloaf chuck andouille pork loin pastrami spare ribs
          pancetta rump. Frankfurter corned beef beef tenderloin short loin meatloaf swine ground round venison.
        </p>
      </section>

      <section id="content2">
      <product
          :product-delivery-fee="22"
          :product-discount="2"
          :product-location="'marzdaran'"
          :product-subtotal="3"
          :product-total-payment="16"
          :product-vat="1"
          :product-date="'22 azar \ sadad '"
          :product-price="4.44"
          :product-name="'KIWI'"
          :product-weight="1"
          :product-image="'https://img.freepik.com/premium-photo/kiwi-fruit-with-cut-half-isolated-white-background_252965-1141.jpg?w=2000'"
        />
      </section>

      <section id="content3">
        <p>
          Bacon ipsum dolor sit amet beef venison beef ribs kielbasa. Sausage pig leberkas, t-bone sirloin shoulder
          bresaola. Frankfurter rump porchetta ham. Pork belly prosciutto brisket meatloaf short ribs.
        </p>
        <p>
          Brisket meatball turkey short loin boudin leberkas meatloaf chuck andouille pork loin pastrami spare ribs
          pancetta rump. Frankfurter corned beef beef tenderloin short loin meatloaf swine ground round venison.
        </p>
      </section>

      <section id="content4">
        <p>
          Bacon ipsum dolor sit amet landjaeger sausage brisket, jerky drumstick fatback boudin ball tip turducken. Pork
          belly meatball t-bone bresaola tail filet mignon kevin turkey ribeye shank flank doner cow kielbasa shankle.
          Pig swine chicken hamburger, tenderloin turkey rump ball tip sirloin frankfurter meatloaf boudin brisket ham
          hock. Hamburger venison brisket tri-tip andouille pork belly ball tip short ribs biltong meatball chuck. Pork
          chop ribeye tail short ribs, beef hamburger meatball kielbasa rump corned beef porchetta landjaeger flank.
          Doner rump frankfurter meatball meatloaf, cow kevin pork pork loin venison fatback spare ribs salami beef
          ribs.
        </p>
        <p>
          Jerky jowl pork chop tongue, kielbasa shank venison. Capicola shank pig ribeye leberkas filet mignon brisket
          beef kevin tenderloin porchetta. Capicola fatback venison shank kielbasa, drumstick ribeye landjaeger beef
          kevin tail meatball pastrami prosciutto pancetta. Tail kevin spare ribs ground round ham ham hock brisket
          shoulder. Corned beef tri-tip leberkas flank sausage ham hock filet mignon beef ribs pancetta turkey.
        </p>
      </section>


    </main>

  </div>
</template>

<script>
import product from "@/components/Product.vue";
export default {
  name: 'cardPanel',
  components:{
    product,
  }
}
</script>

<style lang="scss" scoped>
.headerContainer {
  width: 800px;
  margin: auto;

  .header {
    display: flex;
    justify-content: space-between;

    .headerTitle {
      font-weight: bold;
    }

    .icons {
      width: 80px;
      display: flex;
      align-items: center;

      .headerBtn {
        padding-left: 5px;

        .icon {
          max-width: 20px;
          max-height: 20px;
        }
      }


    }
  }
}

*, *:before, *:after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
}

body {
  font: 14px/1 'Open Sans', sans-serif;
  color: #555;
  background: #eee;
}

h1 {
  padding: 50px 0;
  font-weight: 400;
  text-align: center;
}

p {
  margin: 0 0 20px;
  line-height: 1.5;
}

main {
  min-width: 320px;
  max-width: 800px;
  margin: 0 auto;
  background: #fff;
}

section {
  display: none;
  padding: 20px 0 0;
  border-top: 1px solid #ddd;
}

input {
  display: none;
}

label {
  display: inline-block;
  margin: 0 0 -1px;
  padding: 15px 25px;
  font-weight: 600;
  text-align: center;
  color: #bbb;
  border: 1px solid transparent;
}

label:before {
  font-family: fontawesome;
  font-weight: normal;
  margin-right: 10px;
}

/*label[for*='1']:before {*/
/*  content: '\f1cb';*/
/*}*/

/*label[for*='2']:before {*/
/*  content: '\f17d';*/
/*}*/

/*label[for*='3']:before {*/
/*  content: '\f16b';*/
/*}*/

/*label[for*='4']:before {*/
/*  content: '\f1a9';*/
/*}*/
/*label[for*='5']:before {*/
/*  content: '\f1a9';*/
/*}*/

label:hover {
  color: #555;
  cursor: pointer;
}

input:checked + label {
  color: purple;
  border-bottom: 2px solid purple;
  border-top: 1px solid #fff;
}

#tab1:checked ~ #content1,
#tab2:checked ~ #content2,
#tab3:checked ~ #content3,
#tab4:checked ~ #content4,
#tab5:checked ~ #content5 {
  display: block;
}

@media screen and (max-width: 650px) {
  label {
    font-size: 0;
  }

  label:before {
    margin: 0;
    font-size: 18px;
  }
}

@media screen and (max-width: 400px) {
  label {
    padding: 15px;
  }
}
</style>
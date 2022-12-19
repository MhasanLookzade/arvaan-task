<template>
  <div class="product">
    <div class="productHeader row">
      <div class="productDetails col ">
        <img :src="Product.image" width="100" height="100" alt="product" style="background-color: white">
        <div class="productDet">
          <p class="productName">{{ Product.name }}</p>
          <p class="productWeight">{{Product.weight}}&nbsp;KG</p>
          <p class="productPrice">$&nbsp;{{Product.price}}</p>
        </div>

      </div>
      <div class="productVaz col">
        <button  class="productBtn">compeleted</button>
      </div>
    </div>
    <div class="productBody">
      <button @click="showProduct(Product.btnId)"  :id="Product.btnId" class="productMainBtn">
        <b-icon icon="chevron-compact-down" aria-hidden="true"></b-icon>
      </button>
      <div :id="Product.id"  class="details row">
        <div class="line"></div>
        <div class="static col">
          <p>Date & Time</p>
          <p>Location</p>
          <p>Subtotal</p>
          <p>Delivery Fee</p>
          <p>Discount</p>
          <p>VAT(5%)</p>
          <p style="font-weight: bold;font-size: 22px;">Total Payment</p>
        </div>
        <div class="dynamic col">
          <p>{{Product.date}}</p>
          <p>{{Product.location}}</p>
          <p>${{Product.subtotal}}</p>
          <p>${{Product.deliveryFee}}</p>
          <p>${{Product.discount}}</p>
          <p>${{Product.vat}}</p>
          <p style="font-weight: bold;font-size: 22px;color: purple">${{Product.totalPayment}}</p>
        </div>
        <button  class="receiptBtn">View E-Receipt</button>
        <button @click="hideProduct(Product.btnId)"  :id="Product.btnId" class="productMainBtn">
          <b-icon icon="chevron-compact-up" aria-hidden="true"></b-icon>
        </button>
      </div>
    </div>

  </div>

</template>

<script>
import product from "@/components/Product.vue";

export default {
  name: "Product-shop",
  methods: {
    showProduct(id) {
      const targetDiv = document.getElementById(this.Product.id);
      const btn = document.getElementById(id);
      targetDiv.style.display = "flex";
      btn.style.display = "none"
    },
    hideProduct(id) {
      const targetDiv = document.getElementById(this.Product.id);
      const btn = document.getElementById(id);
      targetDiv.style.display = "none";
      btn.style.display = "block"
    },
    product() {
      return product
    }
  },
  props: {
    ProductBtnId:Number,
    ProductId:String,
    ProductImage: String,
    ProductName: String,
    ProductPrice: Number,
    ProductWeight: Number,
    ProductDate:String,
    ProductLocation:String,
    ProductSubtotal:Number,
    ProductDeliveryFee:Number,
    ProductDiscount:Number,
    ProductVat:Number,
    ProductTotalPayment:Number
  },
  data() {
    return {
      Product:{
        btnId:this.ProductBtnId,
        id:this.ProductId,
        image:this.ProductImage,
        name:this.ProductName,
        weight: this.ProductWeight,
        price:this.ProductPrice,
        date:this.ProductDate,
        location:this.ProductLocation,
        subtotal:this.ProductSubtotal,
        deliveryFee:this.ProductDeliveryFee,
        discount:this.ProductDiscount,
        vat:this.ProductVat,
        totalPayment:this.ProductTotalPayment
      },
    }
  }
}
</script>

<style lang="scss" scoped>
.product{
  //background-color: #bbbbbb;
  //border-radius: 15px;
  .productHeader{
    .productDetails{
      display: flex;
      .productDet{
        padding-left: 10px;
        .productName{
          font-weight: bold;
          font-size: 16px;
          margin-bottom: 5px;
          margin-top: 5px;
        }
        .productWeight{
          font-size: 12px;
          font-weight: normal;
          margin-bottom: 8px;
        }
        .productPrice{
          font-weight: bold;
          font-size: 16px;
          margin-bottom: 0;
        }
      }
    }
    .productVaz{
      display: flex;
      align-items: center;
      justify-content: end;
      .productBtn{
        border: 0;
        box-shadow: none;
        color: white;
        width: 150px;
        height: 35px;
        background-color: green;
        border-radius: 10px;
      }
    }
  }

  .productBody{
    .productMainBtn{
      margin-top: 5px;
      width: 100%;
      border: 0;
      box-shadow: none;
      height: 35px;
      border-radius: 10px;
    }
    .details{
      justify-content: space-between;
      display: none;
      .line{
        width: 100%;
        height: 15px;
        border-top: 1px solid lightgrey;
      }
      .dynamic{
        align-items: self-end;
        display: flex;
        flex-direction: column;
        justify-content: end;
      }
      .static{
        align-items: self-start;
        display: flex;
        flex-direction: column;
        justify-content: start;
      }
      .receiptBtn{
        border: 0;
        box-shadow: none;
        color: white;
        width: 100%;
        height: 55px;
        background-color: purple;
        border-radius: 10px;
      }
    }
  }
}
</style>
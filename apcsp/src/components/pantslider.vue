  <template>
    <div>
      <transition-group name="fade" tag="div">
        <div>
          <img :src="currentImg"/>
        </div>
      </transition-group>
      <a class="prev" @click="prev" href="#">&#10094; </a>
      <a class="next" @click="next" href="#">&#10095; </a>
    </div>
  </template>
  
  <script>
  export default {
    name: "PantSlider",
    data() {
      return {
        images: [
          "https://assets.theplace.com/image/upload/t_pdp_img_m,f_auto,q_auto/v1/ecom/assets/products/tcp/2044158/2044158_10.jpg",
          "https://cdn.shopify.com/s/files/1/0214/3706/products/001SHH801001_OLD_A_1024x.jpg?v=1630616666",
          "https://m.media-amazon.com/images/I/91PuI8YmFSL._AC_UL320_.jpg",
          "https://imgprd19.hobbylobby.com/9/ff/7b/9ff7b3226495f1a49d4a66bd8110f62b9660e2e3/350Wx350H-620831-0122.jpg",
          "https://balenciaga.dam.kering.com/m/109eb6f465f470db/Medium-6573954A8B81000_F.jpg?v=8",
          "https://www.apetogentleman.com/wp-content/uploads/2020/05/bestpolos9.jpg",
          "https://hawaiian-shirt-shop.co.uk/wp-content/uploads/2017/06/HSS147-Premium-Orchids-Red.jpg",
          "https://cdn.lookastic.com/navy-v-neck-t-shirt-original-1304817.jpg"
      ],
        timer: null,
        currentIndex: 0
      };
    },
    mounted: function() {
      this.startSlide();
    },
    methods: {
      startSlide: function() {
        this.timer = setInterval(this.next, 4000);
      },
      next: function() {
        this.currentIndex += 1;
      },
      prev: function() {
        this.currentIndex -= 1;
      }
    },
    computed: {
      currentImg: function() {
        return this.images[Math.abs(this.currentIndex) % this.images.length];
      }
    }
  };
  </script>
  
  <style scoped>
  .fade-enter-active,
  .fade-leave-active {
    transition: all 0.9s ease;
    overflow: hidden;
    visibility: visible;
    position: absolute;
    width:100%;
    opacity: 1;
  }
  .fade-enter,
  .fade-leave-to {
    visibility: hidden;
    width:100%;
    opacity: 0;
  }
  img {
    margin: 3rem;
    height:20rem;
    width:20rem;
  }
  .prev, .next {
    cursor: pointer;
    position: absolute;
    top: 40%;
    width: auto;
    padding: 16px;
    color: rgb(172, 30, 30);
    font-weight: bold;
    font-size: 18px;
    transition: 0.7s ease;
    border-radius: 0 4px 4px 0;
    text-decoration: none;
    user-select: none;
  }
  .next {
    right: 0;
  }
  .prev {
    left: 0;
  }
  .prev:hover, .next:hover {
    background-color: rgba(0,0,0,0.9);
  }</style>
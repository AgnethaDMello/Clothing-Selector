<!-- <template>
    <div>
      <transition-group name="fade" tag="div">
        <div>
          <h2>{{ name }}</h2>
      <img v-bind:src="image" class="image" alt="clothing images" />
      <p>{{ desc }}</p>
        </div>
      </transition-group>
    </div>
  </template>
  
  <script>
  export default {
    name: "Slider",
    props: {
      name: String,
      type: String,
      image: String,
      desc: String,
    },
    
  };
  
  </script>
  
<style scoped>
      .image {
  width: 12rem;
  height: 12rem;
}
  </style> -->
  <template>
    <div>
      <transition-group name="fade" tag="div">
        <div>
          <img :src="currentImg" />
        </div>
      </transition-group>
      <a class="prev" @click="prev" href="#">&#10094; </a>
      <a class="next" @click="next" href="#">&#10095; </a>
    </div>
  </template>
  
  <script>
import bye from "../images/bye.jpg";
import hi from "../images/hi.jpg";
  export default {
    name: "Slider",
    data() {
      return {
        images: [
          bye,
          hi
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
    height:200px;
    width:50%;
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
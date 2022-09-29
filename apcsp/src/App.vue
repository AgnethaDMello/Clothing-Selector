<template>
  <body class="light">
    <div>
        <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300&display=swap" rel="stylesheet">
        <h1 id="header">Clothing Gallery!</h1>
        <div id="whole">
          <button id="btn1" class="btn1" @click="button1 = !button1">Hide Shirts</button>
        <button id="btn2" class="btn2" @click="button2 = !button2">Hide Pants</button>
        <div class="row">
        <div class="column" v-if="button1">
  <div v-for="(item, index) in items"
        :key="item.name"
            :name="item.name"
            :image="item.img"
            :desc="item.desc"
            :index="index">
            <div class="cards" v-if="item.shirt">
              <h2 class="shirtnames">
    {{ item.name }}
            </h2>
            <img class="shirtimgs" :src="item.img"/>
            <h3 class="light" >
    {{ item.desc }}
            </h3>
          </div>
  <div class="hidden" v-else>
            </div>
  </div>
</div>
<div class="row">
        <div id="pantcolumn" class="column" v-if="button2">
  <div v-for="(item, index) in items"
        :key="item.name"
            :name="item.name"
            :image="item.img"
            :desc="item.desc"
            :index="index">
            <div class="cards" v-if="item.pant">
              <h2 class="shirtnames">
    {{ item.name }}
            </h2>
            <img class="shirtimgs" :src="item.img"/>
            <h3 class="light" >
    {{ item.desc }}
            </h3>
          </div>
  <div class="hidden" v-else>
            </div>
  </div>
        </div>
      </div>
  </div>
</div>
</div>
  </body>
    </template>
<script>
export default {
    name: "Home",
    data() {
    return {
      button1: true,
      button2: true,
      items: [
        {
            name: "Button Down",
            shirt: true,
            img: "https://assets.vogue.com/photos/5d76ece4b149a10008466ddc/1:1/w_640,h_640,c_limit/slide.jpg",
            desc: "A white button-down shirt, a classic for formal looks.",
        },
        {
            name: "Flannel",
            shirt: true,
            img: "https://cdn.shopify.com/s/files/1/0214/3706/products/001SHH801001_OLD_A_1024x.jpg?v=1630616666",
            desc: "A green plaid shirt, comfortable and great for the outdoors.",
        },
        {
            name: "T-Shirt",
            shirt: true,
            img: "https://m.media-amazon.com/images/I/91PuI8YmFSL._AC_UL320_.jpg",
            desc: "A simple plain yellow t-shirt, made for hot, sunny days.",
        },
        {
            name: "Long Sleeve",
            shirt: true,
            img: "https://imgprd19.hobbylobby.com/9/ff/7b/9ff7b3226495f1a49d4a66bd8110f62b9660e2e3/350Wx350H-620831-0122.jpg",
            desc: "A black long sleeve shirt, versatile and can be paired with almost anything.",
        },
        {
            name: "Tank Top",
            shirt: true,
            img: "https://balenciaga.dam.kering.com/m/109eb6f465f470db/Medium-6573954A8B81000_F.jpg?v=8",
            desc: "A black tank top, designed for hot weather and workouts.",
        },
        {
            name: "Polo Shirt",
            shirt: true,
            img: "https://www.apetogentleman.com/wp-content/uploads/2020/05/bestpolos9.jpg",
            desc: "A polo short sleeve shirt, a staple in the closet of golfers.",
        },
        {
            name: "Hawaiian Shirt",
            shirt: true,
            img: "https://hawaiian-shirt-shop.co.uk/wp-content/uploads/2017/06/HSS147-Premium-Orchids-Red.jpg",
            desc: "A bright, colorful hawaiian shirt, fun and perfect for tropical vacations.",
        },
        {
            name: "V-Neck",
            shirt: true,
            img: "https://oldnavy.gap.com/webcontent/0028/497/539/cn28497539.jpg",
            desc: "A navy blue v-neck shirt, simple yet classy.",
        },
        {
            name: "Track Pant",
            pant: true,
            img: "https://underarmour.scene7.com/is/image/Underarmour/PS1357201-001_HF?rp=standard-0pad|pdpMainDesktop&scl=1&fmt=jpg&qlt=85&resMode=sharp2&cache=on,on&bgc=F0F0F0&wid=566&hei=708&size=566,708 ",
            desc: "A black track pant, comfortable and hugs your legs well while exercising.",
        },
        {
            name: "Sweatpants",
            pant: true,
            img: "https://media.gq.com/photos/6036b7eeb86c65eb745394a8/master/w_2000,h_1333,c_limit/Goodwear-fleece-sweatpants-with-side-pockets.jpg",
            desc: "A grey sweatpant, cozy and snug for being both lazy and active.",
        },
        {
            name: "Straight Pants",
            pant: true,
            img: "https://img.abercrombie.com/is/image/anf/KIC_156-2331-0775-410_prod1?policy=product-medium ",
            desc: "A tan straight legged pant, great for formal occassions.",
        },
        {
            name: "Flared",
            pant: true,
            img: "https://cdn-images.farfetch-contents.com/17/88/99/09/17889909_39807318_300.jpg",
            desc: "A black flared legging, modern and chic, plus they pair well with many shirts.",
        },
        {
            name: "Skinny Jean",
            pant: true,
            img: "https://i.pinimg.com/originals/98/12/ff/9812ff098d3e16dd61fad13db217c50f.jpg",
            desc: "A dark blue skinny jean, a continuity in the fashion world for many years.",
        },
        {
            name: "Wide Jean",
            pant: true,
            img: "https://media.companys.com/images/light-blue-elmagz-hw-wide-jeans.jpg?i=AP6cq-RN2Ag/428509&mw=610",
            desc: "A light blue wide jean, covers your leg shape and can become baggy if sized up.",
        },
        {
            name: "Distressed Jean",
            pant: true,
            img: "https://cdn-fnknc.nitrocdn.com/jwqHRGAzpUgGskUSHlppNQzwuXgXIKwg/assets/static/optimized/rev-c69cd9d/wp-content/uploads/2022/08/Amiri_BestRippedJeans.jpg",
            desc: "A washed out light blue jean with tears, a bold punk statement.",
        },
        {
            name: "Cargo Pant",
            pant: true,
            img: "https://admin.kaufmannstatic.com/Images/177940_seaweed_01-T20220713013313.jpg?i=177940_seaweed_01-T20220713013313.jpg&w=300&h=300&bgcolor=ffffff",
            desc: "Light grey-green cargo pants, practical for work and great for streetstyle.",
        },
      ],
    }
  },
    mounted: function() {
    this.buttonClick();
  },
  methods: {
    buttonClick: function() {
      const btn1 = document.getElementById('btn1');
      // ✅ Toggle button text on click
btn1.addEventListener('click', function handleClick() {
  const initialText = 'Hide Shirts';

  if (btn1.textContent.toLowerCase().includes(initialText.toLowerCase())) {
    btn1.textContent = 'Show Shirts';
  } else {
    btn1.textContent = initialText;
  }
});
      const btn2 = document.getElementById('btn2');
      // ✅ Toggle button text on click
btn2.addEventListener('click', function handleClick() {
  const initialText = 'Hide Pants';

  if (btn2.textContent.toLowerCase().includes(initialText.toLowerCase())) {
    btn2.textContent = 'Show Pants';
  } else {
    btn2.textContent = initialText;
  }
});
    },
}
}
</script>

<style scoped>
  * {
  box-sizing: border-box;
}
.column {
  float: left;
  width: 20rem;
  margin-left: 22%;
}
.row:after {
  content: "";
  display: table;
  clear: both;
}
button,
button:link,
button:visited {
    text-transform: uppercase;
    text-decoration: none;
    padding: 1rem 2.5rem;
    display: inline-block;
    margin-bottom: 2rem;
    font-size: var(--h3);
    border: none;
    border-radius: 10rem;
    transition: all 0.2s;
    color: var(--cool);
}
button:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 0.5rem rgba(0, 0, 0, 0.2);
}    

#header{
  font-size: var(--h1);
  margin-left: 28.5rem;
  width: 50rem;
  color: var(--header)
}
img {
  width: 20rem;
  height: 20rem;
}
.cards{
  margin-bottom: 5rem;
  width: 20rem;
}
.btn1{
  margin-left: 20rem;
}
.btn2{
  margin-left: 23rem;
}
#whole{
  display: inline;
}
#pantcolumn{
  position: absolute;
  margin-left: 54.5rem;
}
h2{
  text-align: center;
  margin-bottom:1rem;
  color: var(--text);

}
h3{
  text-align: center;
  margin-top: 1rem;
  color: var(--text);
}
</style>
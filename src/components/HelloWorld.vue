<script setup>
import { ref, } from 'vue'
const characters = ref([
  {
    name: "Akuma",
    id: "akuma",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/akuma.png'
  }, {
    name: "Balrog",
    id: "balrog",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/balrog.png'
  }, {
    name: "M. Bison",
    id: "bison",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/bison.png'
  }, {
    name: "Blanka",
    id: "blanka",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/blanka.png'
  }, {
    name: "Cammy",
    id: "cammy",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/cammy.png'
  }, {
    name: "Chun Li",
    id: "chunli",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/chunli.png'
  }, {
    name: "Dhalsim",
    id: "dhalsim",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/dhalsim.png'
  }, {
    name: "E. Honda",
    id: "ehonda",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/ehonda.png'
  }, {
    name: "Evil Ryu",
    id: "evilryu",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/ryu.pnevilg.png'
  }, {
    name: "Guile",
    id: "guile",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/guile.png'
  }, {
    name: "Ken",
    id: "ken",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/ken.png'
  }, {
    name: "Ryu",
    id: "ryu",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/ryu.png'
  }, {
    name: "Sagat",
    id: "sagat",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/sagat.png'
  }, {
    name: "T-Hawk",
    id: "thawk",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/t-hawk.png'
  }, {
    name: "Vega",
    id: "vega",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/vega.png'
  }, {
    name: "Zangief",
    id: "zangief",
    imgSrc: 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/zangief.png'
  }
])
const aciveId = ref(null)
function handleActive(id) {
  aciveId.value = id
}

</script>

<template>
  <div class="container"><img class="sf-logo"
      src="https://vignette2.wikia.nocookie.net/ssb/images/f/f6/SF_Logo.png/revision/latest?cb=20150614010256" />
    <h1 class="title">Player Select</h1>
    <div class="select-container" id="selectContainer">
      <button v-for="item in characters" :key="item.id" :rel="item.name" class="character "
        :class="{ active: item.id == aciveId }" :id="item.id" @click="handleActive(item.id)">
        <img class="character__img" :src="item.imgSrc" />
        <p class="character__name">{{ item.name }}</p>
      </button>
    </div>
  </div>
  <audio autobuffer="autobuffer" autoplay="autoplay" loop="true">
    <source src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/813538/02.%20Player%20Select.mp3" type="audio/ogg" />
  </audio>
  <footer class="list-footer">Made with <span class="heart">&hearts; </span>for my homies</footer>



</template>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Merriweather:400,700");

html {
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

html,
body {
  width: 100%;
  height: 100%;
}

body {
  background: #0d0d3a;
  font-family: "Merriweather", serif;
}

a {
  text-decoration: none;
  margin: 0;
  padding: 0;
}

.sf-logo {
  width: 150px;
  margin: 1em auto;
  display: block;
}

.container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 5vh 0 80px;
}

.title {
  text-align: center;
  text-transform: uppercase;
  color: #dac751;
  letter-spacing: 0.1em;
  text-shadow: 0px 2px 2px rgba(255, 255, 255, 0.6);
}

.select-container {
  display: grid;
  grid-template-columns: repeat(8, 100px);
  grid-column-gap: 8px;
  grid-row-gap: 8px;
  margin: 1em auto 3em;
  background: rgba(255, 255, 255, 0.5);
  padding: 4px 4px;
}

@media screen and (max-width: 900px) {
  .select-container {
    grid-template-columns: repeat(4, 100px);
  }
}

@media screen and (max-width: 600px) {
  .select-container {
    grid-template-columns: repeat(4, 76.9230769231px);
  }
}

.character {
  width: 100px;
  background: rgba(255, 255, 255, 0.5);
  cursor: pointer;
  position: relative;
  text-align: center;
  padding: 0;
  border: 0;
  margin: 0;
  display: inline-flex;
}

@media screen and (max-width: 600px) {
  .character {
    width: 76.9230769231px;
  }
}

.character:focus,
.character:active {
  outline: 0;
}

.character__name {
  position: absolute;
  width: 100%;
  bottom: 0;
  display: none;
}

.character__img,
.character__name {
  margin: 0;
  padding: 0;
}

.character__img {
  filter: grayscale(0.84);
  width: 100%;
}

.character.active {
  transform: scale(1.05);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.2);
  z-index: 100;
}

.character.active .character__name {
  display: block;
  width: 100%;
  background: #e3231e;
  color: white;
  opacity: 0.7;
  margin-top: 0.8em;
  font-size: 0.7em;
  text-transform: uppercase;
  font-weight: 700;
  padding: 0.3em 0;
}

.character.active:after {
  content: "1P";
  position: absolute;
  text-align: center;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 36px;
  color: #e3231e;
  font-weight: 700;
  text-shadow: 0px 0px 5px rgb(255, 255, 255);
}

.character.active .character__img {
  filter: grayscale(0);
  outline: 4px solid white;
  animation: flash 300ms linear;
}

.list-footer {
  background: linear-gradient(to top, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0));
  font-family: Tahoma, sans-serif;
  color: white;
  text-align: center;
  font-size: 0.7em;
  padding: 1em;
  text-transform: uppercase;
  font-weight: 700;
  letter-spacing: 0.1em;
  position: fixed;
  bottom: 0;
  width: 100%;
}

.list-footer .heart {
  color: tomato;
  font-size: 2em;
  vertical-align: middle;
}

@keyframes flash {
  0% {
    filter: brightness(100%);
  }

  20% {
    filter: brightness(150%);
  }

  40% {
    filter: brightness(100%);
  }

  60% {
    filter: brightness(150%);
  }

  80% {
    filter: brightness(100%);
  }

  100% {
    filter: brightness(150%);
  }
}

/*# sourceMappingURL=index.css.map */
</style>

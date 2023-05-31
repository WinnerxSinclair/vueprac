<template>
  <div class="xd">
    <div>
      <button :class="{ active: Type === 'RFI' }" @click="Type = 'RFI'">RFI</button>
      <button :class="{ active: Type === 'Defend' }" @click="Type = 'Defend'">Defend</button>
    </div>

    <div>
      <button :class="{ active: StackDepth === '15BB' }" @click="StackDepth = '15BB'">15BB</button>
      <button :class="{ active: StackDepth === '25BB' }" @click="StackDepth = '25BB'">25BB</button>
      <button :class="{ active: StackDepth === '40BB' }" @click="StackDepth = '40BB'">40BB</button>
      <button :class="{ active: StackDepth === '60BB' }" @click="StackDepth = '60BB'">60BB</button>
    </div>

    <div>
      <button :class="{ active: HeroPosition === 'SB' }" @click="HeroPosition = 'SB'">SB</button>
      <button :class="{ active: HeroPosition === 'BB' }" @click="HeroPosition = 'BB'">BB</button>
      <button :class="{ active: HeroPosition === 'BU' }" @click="HeroPosition = 'BU'">BU</button>
      <button :class="{ active: HeroPosition === 'CO' }" @click="HeroPosition = 'CO'">CO</button>
      <button :class="{ active: HeroPosition === 'HJ' }" @click="HeroPosition = 'HJ'">HJ</button>
      <button :class="{ active: HeroPosition === 'LJ' }" @click="HeroPosition = 'LJ'">LJ</button>
      <button :class="{ active: HeroPosition === 'UTG+2' }" @click="HeroPosition = 'UTG+2'">UTG+2</button>
      <button :class="{ active: HeroPosition === 'UTG+1' }" @click="HeroPosition = 'UTG+1'">UTG+1</button>
      <button :class="{ active: HeroPosition === 'UTG' }" @click="HeroPosition = 'UTG'">UTG</button>
    </div>

    <div>
      <button :class="{ active: VillianPosition === 'SB' }" @click="VillianPosition = 'SB'">SB</button>
      <button :class="{ active: VillianPosition === 'BB' }" @click="VillianPosition = 'BB'">BB</button>
      <button :class="{ active: VillianPosition === 'BU' }" @click="VillianPosition = 'BU'">BU</button>
      <button :class="{ active: VillianPosition === 'CO' }" @click="VillianPosition = 'CO'" :disabled="disableCOButton">CO</button>
      <button :class="{ active: VillianPosition === 'HJ' }" @click="VillianPosition = 'HJ'" :disabled="disableHJButton">HJ</button>
      <button :class="{ active: VillianPosition === 'LJ' }" @click="VillianPosition = 'LJ'" :disabled="disableLJButton">LJ</button>
      <button :class="{ active: VillianPosition === 'UTG+2' }" @click="VillianPosition = 'UTG+2'" :disabled="disableUTG2Button">UTG+2</button>
      <button :class="{ active: VillianPosition === 'UTG+1' }" @click="VillianPosition = 'UTG+1'" >UTG+1</button>
      <button :class="{ active: VillianPosition === 'UTG' }" @click="VillianPosition = 'UTG'" :disabled="disableUTGButton">UTG</button>
    </div>

    <div class="image-container">
      <img :src="getPictureUrl">
      <img :src="getPictureUrlxdd">
      <img :src="getPictureUrlxd">
    </div>
  </div>
</template>

<style scoped>
.xd {
  text-align: left;
  margin-left: 20px;
}

.image-container {
  display: flex;
}

img {
  max-width: 550px;
}

button {
  margin-right: 5px;
}

button.active {
  background-color: #ccc;
}
</style>

<script>
export default {
  data() {
    return {
      Type: '',
      StackDepth: '',
      HeroPosition: '',
      VillianPosition: '',
    };
  },
  computed: {
    getPictureUrl() {
      let pictureUrl = '';
      if (this.Type === 'RFI') {
        pictureUrl = `${this.Type}_${this.StackDepth}_${this.HeroPosition}.png`;
      } else if (this.Type === 'Defend') {
        pictureUrl = `${this.Type}_${this.StackDepth}_${this.HeroPosition}_${this.VillianPosition}.png`;
      }
      return pictureUrl;
    },
    getPictureUrlxd() {
      let pictureUrlxd = '';
      if (this.Type === 'RFI') {
        pictureUrlxd = `${this.Type}_${this.StackDepth}_${this.HeroPosition}_${this.VillianPosition}_3b.png`;
      } else if (this.Type === 'Defend') {
        pictureUrlxd = `${this.Type}_${this.StackDepth}_${this.HeroPosition}_${this.VillianPosition}_4b.png`;
      }
      return pictureUrlxd;
    },
    getPictureUrlxdd() {
      const pictureUrlxdd = `${this.Type}_${this.StackDepth}_${this.HeroPosition}_${this.VillianPosition}_3bb.png`;
      return pictureUrlxdd;
    },
    disableCOButton() {
      return this.Type === 'RFI';
      
    },
    disableLJButton() {
      return this.Type === 'RFI';
      
    },
    disableUTG2Button() {
      return this.Type === 'RFI';
      
    },
    disableUTGButton() {
      return this.Type === 'RFI';
      
    },
    disableHJButton() {
      return this.Type === 'Defend';
      
    },
   
   
  },
};
</script>


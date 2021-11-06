<template>
  <div>
    <Header />
    <audio ref="bus" src="../../sounds/bus.mp3" class="bus" />
    <audio id="upperBus" ref="upperBus" src="../../sounds/upperBus.mp3" class="upperBus" />
    <div class="piano">
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound($event)" id="pianoKey" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound(event)" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        <div @click="playUpperSound()" class="pianoUpperKey">
        </div>
      </div>
      <div @click="playSound()" class="pianoKey">
        
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'Home',
  mounted(){

  },
  methods: {
    playSound(event){
      this.$refs.bus.play()
    },
    playUpperSound() {
      // console.log(`this.$refs.upperBus: ${Object.values(this.$refs.upperBus)}`)
      console.log(`this.$refs.upperBus: ${document.getElementById("upperBus").volume}`)
      this.$refs.upperBus.play()
    }
  },
  components: {
    Header,
    Footer
  }
}
</script>
<style scoped>

  .piano {
    margin: 25px auto;
    display: flex;
    height: 500px;
    width: 100%;
    justify-content: center;
  }

  .pianoKey {
    border: 1px solid rgb(215, 215, 215);
    width: 25px;
    cursor: pointer;
  }

  .pianoUpperKey {
    background-color: rgb(0, 0, 0);
    width: 8px;
    height: 75px;
    float: right;
    position: relative;
    left: 5px;
    border-radius: 0px 0px 5px 5px;
  }

  .bus, .upperBus {
    display: none;
  }

</style>
<template>
  <div>
    <Header />
    <audio ref="bus" src="../../sounds/bus.mp3" class="bus" />
    <audio id="upperBus" ref="upperBus" src="../../sounds/upperBus.mp3" class="upperBus" />
    <div class="piano">
      <div v-for="pianoKey in pianoKeys" :id="`pianoKeyId_${busHotkeys[pianoKey]}`" :key="pianoKey" @click="playSound(2 / pianoKeys * pianoKey)" class="pianoKey" :data-bus-hot-keys-index="pianoKey" data-bus-is-minor="true">
        <div v-if="pianoKey < pianoKeys" @click="playUpperSound(2 / pianoKeys * pianoKey)" class="pianoUpperKey"  :id="`pianoKeyId_${upperBusHotkeys[pianoKey]}`" :data-bus-hot-keys-index="pianoKey" data-bus-is-major="true">
        </div>
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
  data(){
    return {
      pianoKeys: 26,
      busHotkeys: {
        1: 'q',
        2: 'w',
        3: 'e',
        4: 'r',
        5: 't',
        6: 'y',
        7: 'u',
        8: 'i',
        9: 'o',
        10: 'p',
        11: '[',
        12: ']',
        13: 'a',
        14: 's',
        15: 'd',
        16: 'f',
        17: 'g',
        18: 'h',
        19: 'j',
        20: 'k',
        21: 'l',
        22: '\;',
        23: '\'',
        24: 'z',
        25: 'x',
        26: 'c'
      },
      upperBusHotkeys: {
        1: '\$',
        2: 'v',
        3: 'b',
        4: 'n',
        5: 'm',
        6: '\,',
        7: '\.',
        8: '\/',
        9: '1',
        10: '2',
        11: '3',
        12: '4',
        13: '5',
        14: '6',
        15: '7',
        16: '8',
        17: '9',
        18: '\/',
        19: '\*',
        20: '\-',
        21: '\+',
        22: '\`',
        23: 'Escape',
        24: 'Enter',
        25: '\%'
      }
    }
  },
  mounted(){
    document.body.addEventListener('keyup', event => {
      let activePianoKey = document.getElementById(`pianoKeyId_${event.key}`)
      if(activePianoKey.hasAttribute('data-bus-is-minor')) {
        activePianoKey.style.backgroundColor = 'rgb(225, 225, 225)'
      } else if(activePianoKey.hasAttribute('data-bus-is-major')) {
        activePianoKey.style.backgroundColor = 'rgb(125, 125, 125)'
      }
      this.playSound(2 / this.pianoKeys * activePianoKey.getAttribute('data-bus-hot-keys-index'))
      if(activePianoKey.hasAttribute('data-bus-is-minor')) {
        setTimeout(() => activePianoKey.style.backgroundColor = 'rgb(255, 255, 255)', 300)
      } else if(activePianoKey.hasAttribute('data-bus-is-major')) {
        setTimeout(() => activePianoKey.style.backgroundColor = 'rgb(0, 0, 0)', 300)
      }
    })
  },
  methods: {
    playSound(rate){
      // this.$refs.bus.play()
      let minor = new Audio(this.$refs.bus.src)
      minor.playbackRate = rate
      minor.play()
    },
    playUpperSound(rate) {
      // console.log(`this.$refs.upperBus: ${Object.values(this.$refs.upperBus)}`)
      console.log(`this.$refs.upperBus: ${document.getElementById("upperBus").volume}`)
      // this.$refs.upperBus.play()
      let major = new Audio(this.$refs.upperBus.src)
      major.playbackRate = rate
      major.play()
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
    background-color: rgb(255, 255, 255);
  }

  .pianoKey:hover {
    background-color: rgb(240, 240, 240);
  }

  .pianoKey:active {
    background-color: rgb(225, 225, 225);
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

  .pianoUpperKey:hover {
    background-color: rgb(75, 75, 75);
  }

  .pianoUpperKey:active {
    background-color: rgb(125, 125, 125);
  }

  .bus, .upperBus {
    display: none;
  }

</style>
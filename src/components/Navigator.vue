<template lang="html">
  <div id="navigator">
    <button id="reset" v-on:click="restart">{{ reset }}</button>
    <span id="message" :style="{color: messageColor}">{{ message }}</span>
    <button id="easy" v-on:click="changeToEasy()">easy</button>
    <button id="hard" class="selected" v-on:click="changeToHard()">hard</button>
  </div>
</template>

<script lang="js">

export default {
  name: 'src-components-navigator',
  props: {
    message: {
      type: String
    },
    reset: {
      type: String
    },
    messageColor: {
      type: String,
    }
  },
  mounted() {
  },
  data() {
    return {}
  },
  methods: {
    changeToEasy() {
      document.querySelector('#easy').classList.add('selected')
      document.querySelector('#hard').classList.remove('selected')
      this.$emit('changeToEasy', 'easy')
    },
    changeToHard() {
      document.querySelector('#easy').classList.remove('selected')
      document.querySelector('#hard').classList.add('selected')
      this.$emit('changeToHard', 'hard')
    },
    restart() {
      this.$emit('restart')
    }
  },
  computed: {}
}


</script>

<style scoped lang="css">
#navigator {
  background: #ffffff;
  height: 30px;
  text-align: center;
  margin: -30px 0 0;
}

#message {
  color: #ffffff;
  display: inline-block;
  width: 20%;
}

button {
  border: none;
  background-color: white;
  font-family: "Montserrat", "Avenir", serif;
  text-transform: uppercase;
  height: 100%;
  font-weight: 700;
  letter-spacing: 1px;
  color: steelblue;
  transition: all 0.3s;
  outline: none;
}

button:hover {
  color: white;
  background-color: steelblue;
}

.selected {
  background-color: steelblue;
  color: white;
}
</style>

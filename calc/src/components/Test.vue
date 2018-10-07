<template>
  <div class="main card">
    <div class="message card-body">
      {{ msg1 }} - {{ msg2 }}
    </div>
    <div class="message card-body">
      こたえ : {{ answer }}
    </div>
    <div class="message card-body">
      <button v-on:click="calc()" class="btn btn-secondary">Answer</button>
      <button v-on:click="start()" class="btn btn-secondary">Next</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Test',
  data () {
    return {
      msg1: 0,
      msg2: 0,
      answer: 0
    }
  },
  methods: {
    start () {
      this.msg1 = randInt(10, 18)
      this.msg2 = randInt(1, 9)
    },
    calc () {
      this.answer = this.msg1 - this.msg2
    }
  }
}

var randInt = function (min = 0, max = 1) {
  return Math.floor(Math.random() * (max + 1 - min)) + min
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.message.card-body {
  font-size: 4rem;
}
</style>

<template>
<v-content>
  <v-container v-if="active === 0" id="lets-go" fluid fill-height pa-0>
    <v-layout column align-center justify-center>
      <v-flex class="text-xs-center white--text" xs3>
        <div class="headline mb-3">Välkommen till</div>
        <div class="display-3">Vinlotteriet</div>
        <v-btn color="primary" class="mt-3" @click="next()">Start</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
  <v-container v-if="active === 1" id="players" fluid fill-height pa-0>
    <v-layout column align-center justify-center>
      <v-flex column class="text-xs-center white--text" xs3>
        <v-btn icon large>
          <v-icon class="minus">fa-wine-glass</v-icon>
        </v-btn>
        <v-btn icon large>
          <v-icon>fa-wine-glass</v-icon>
        </v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</v-content>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function () {
    return {
      active: 0
    }
  },
  methods: {
    next() {
      switch (this.active) {
        case 0:
          this.active = 1
          break;
        case 1:
          
          break;
        case 2:
          
          break;
        case 3:
          
          break;
        default:
          break;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#lets-go {
  background: linear-gradient( rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5) ), url("https://i.imgur.com/enJOoTW.png");
}
h3 {
  margin: 40px 0 0;
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

.display-3 {
  font-family: Great Vibes !important;
}

.minus {
  -webkit-transform: rotate(-135deg);
  -moz-transform: rotate(-135deg);
  -ms-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  transform: rotate(-135deg);
}
</style>

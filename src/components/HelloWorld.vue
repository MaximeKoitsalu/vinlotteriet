<template>
<v-content class="wine-red">
  <v-container v-if="active === 0" id="lets-go" fluid fill-height pa-0>
    <v-layout column align-center justify-center>
      <v-flex class="text-xs-center white--text" xs3>
        <div class="headline mb-3">Välkommen till</div>
        <div class="display-3 wine-font">Vinlotteriet</div>
        <v-btn class="wine-red-light mt-3 white--text" @click="next()">Start</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
  <v-container v-else-if="active === 1" id="players" fluid fill-height pa-0>
    <v-layout pt-4 row wrap align-center justify-center>
      <v-flex xs12 class="white--text text-xs-center">
        <span class="display-3 wine-font">
          Antal Tävlande
        </span>
      </v-flex>
      <v-flex xs12 align-center justify-center class="white--text text-xs-center">
        <v-btn style="vertical-align: super;" icon large @click="participants > 0 ? participants-- : ''">
          <v-icon color="white">remove</v-icon>
        </v-btn>
        <span class="ma-4 wine-font" style="font-size: 56px;">{{ participants }}</span>
        <v-btn style="vertical-align: super;" color="white" @click="participants < 15 ? participants++ : ''" icon large>
          <v-icon>add</v-icon>
        </v-btn>
      </v-flex>
      <v-flex xs12 align-center justify-center class="white--text text-xs-center">
        <transition-group name="fade">
          <v-icon large color="white" class="mx-4 my-1" v-for="index in participants" :key="index">
            fa-wine-glass
          </v-icon>
        </transition-group>
      </v-flex>
      <v-flex xs12 text-xs-center>
        <v-btn class="wine-red-light mt-3 white--text" @click="next()">Next</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
  <v-container fluid fill-height pa-0 v-else>
    <v-layout align-center justify-center>
      <v-progress-circular indeterminate color="white" :width="7" :size="70"></v-progress-circular>
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
      active: 1,
      loading: false,
      participants: 1
    }
  },
  methods: {
    next () {
      switch (this.active) {
        case 0:
        this.active = 666
        setTimeout(() => {
            this.active = 1;
        }, 2000)
          break
        case 1:
          break
        case 2:
          break
        case 3:
          break
        default:
          break
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

.wine-font {
  font-family: Great Vibes !important;
}

.wine-red {
  background: #290101;
  background-color: #290101 !important;
}

.wine-red-light {
  background-color: #690b22 !important;
}

.minus {
  -webkit-transform: rotate(-135deg);
  -moz-transform: rotate(-135deg);
  -ms-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  transform: rotate(-135deg);
}
</style>

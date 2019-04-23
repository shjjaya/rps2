result.vue
<template>
  <div class="card">
      <div class="col-8 text-center">
          <h3 class="card-title">{{ rw.text }}</h3>
          <button class="btn btn-success" @click="playAgain">Play Again</button>
      </div>
  </div>
</template>
<script>
export default {
    name: 'ResultWindow',
    props:['rw'],
    data(){
        return {}
    },
    methods: {
        playAgain(){
            this.$emit('playAgainEvent');
        }
    }
}
</script>

<style lang="css" scoped>

</style>


scoreboard.vue


<template>
    <div class="container">
        <div class="row"><br />
            <h1 align="center" style="color:white;">Rock Paper Scissors <br />Game Board</h1><br /><br />
         </div>
        <div class="row">
            <div class="col-2 text-center" style="color:white;"><h3>Player</h3>
                <h2 style="color:white;">{{score.player}}</h2>
            </div>
            <div class="col-2 text-center">
                <button class="btn btn-warning" @click="resetScore">Reset</button>
            </div>
            <div class="col-2 text-center"><h3 style="color:white;">Computer</h3>
                 <h2 style="color:white;">{{score.cpu}}</h2>
            </div>
        </div>
    </div>
</template>

<script>
 export default {
     name: 'scoreboard',
     props: ['score'],
     data() {
         return {}
     },
     methods: {
         resetScore(){
                this.$emit('resetScoreEvent');
         }
     }
 }
</script>

<style lang="scss">

</style>




choices.vue

<template>
    <div class="card">
        <div class="col-8 text-center">
            <div class="row text-center">
                <div class="col text-center" v-for="(option,index) in options" style="background-color:#32AEA0">
                     <img :src="'src/images/' + option + '.png'" width="55" height="55" @click="makeChoice(index)" />
                     <br /><h4 style="color:white;">{{ option }}</h4>
                </div>

            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'choices',
    data() {
        return {
            options: ['Rock', 'Paper', 'Scissors']
        }
    },
    methods: {
        makeChoice(i) {
            this.$emit('makeChoiceEvent', i)
        }
    }
}
</script>

<style lang="css" scoped>
</style>

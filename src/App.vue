<template>
  <div id="app" style="color:white;">
      <scoreboard :score="score" @resetScoreEvent="resetScore" />
      <choices @makeChoiceEvent= "playRound" v-show="!resultWindow.show" />
      <result-window :rw="resultWindow" @playAgainEvent="newRound" v-show="resultWindow.show" />
  </div>
</template>

<script>
import Scoreboard from './components/scoreboard'
import Choices from './components/Choices'
import ResultWindow from './components/ResultWindow'
export default {
  name: 'app',
  components: { Scoreboard, Choices, ResultWindow },
  data () {
    return {
      score: {
          player: 10,
          cpu: 5,
      },
      resultWindow: {
      text:'',
      show: false
    }
  }
},
methods: {
        resetScore(){
            let reset = confirm('Are you sure you want reset');
            if(reset){
            this.score = { player: 0 ,cpu: 0};
            }
        },
        playRound(playerChoice){
            let  cpuChoice = Math.floor(Math.random() *3);

        // copmare choices -determine winner
        if(playerChoice == cpuChoice) {
            this.showResult('draw');
        } else if((playerChoice - cpuChoice + 3) % 3 == 1) {
            this.showResult('win');
        }else {
            this.showResult('lose');
        }
    },
    showResult(result){

        // show result window
        this.resultWindow.show = true;


        switch(result) {
            case 'draw':
            this.resultWindow.text = 'It\s a Draw!';
            break;

            case 'win':
            this.resultWindow.text = 'you win!';
            this.score.player++;
            break;

            case 'lose':
            this.resultWindow.text = 'you lose!';
            this.score.cpu++;
            break;

        }
    },
    newRound(){

        this.resultWindow.show = false;
    }
  }
}
</script>

<style lang="scss">

</style>

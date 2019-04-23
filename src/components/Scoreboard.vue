<template>
    <div class="container">
        <div class="row" style="background-color:#0F6F64">
            <h1 style="color:white;">Rock Paper Scissors Game Board</h1>
         </div><br /><br />
        <div class="row" style="background-color:#32AEA0">
            <div class="col-4 text-center" style="color:white;"><h3>Player</h3>
                <h2 style="color:white;">{{score.player}}</h2>
            </div>
            <div class="col-4 text-center">
                 <br /><h2> VS </h2>
            </div>

            <div class="col-4 text-center"><h3 style="color:white;">Computer</h3>
                 <h2 style="color:white;">{{score.cpu}}</h2>
            </div>
        </div><br /><br />
        <div class="col text-center">
            <button class="button" @click="resetScore" style="background-color:#0F6F64"><h3 style="color:white;">Reset</h3></button>
            <br /><br /><h4 style="color:white;">Make Your Move</h4>
        </div><br /><br />
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

<template>
  <div class="card-text" style="background-color:#0F6F64">
      <div class="col-12 text-center">
          <h3 class="card-title">{{ rw.text }}</h3><br />
          <button class="button" @click="playAgain" style="background-color:#0F6F64"><h4 style="color:white;">Play Again</h4></button>
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

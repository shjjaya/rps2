<template>
    <div class="card" style="background-color:#0F6F64">
        <div class="col-12 text-center">
            <div class="row" align="center" style="background-color:#0F6F64">
                <div class="col text-center" v-for="(option,index) in options">
                     <img :src="'src/images/' + option + '.png'" width="85" height="85" @click="makeChoice(index)"  style="background-color:#0F6F64" class="image" />
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

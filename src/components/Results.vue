<template>
  <div>
      <p>Reaction Time : {{ score }} ms</p>
      <p>{{ rank }}</p>
  </div>
</template>

<script>
export default {
    props : ['score'],
    data() {
        return {
            rank : null
        }
    },
    mounted() {
    if(this.score < 250) {
        this.rank = "ninja fingers"
      } 
    },
}
</script>

<style>

</style>
<template>
  <form class="baseInput" @submit.prevent="">
      <label for="input">Enter your dates</label>
      <input type="text" name="input" id="input" v-model="theDate">
      <button @click='getDate'>Show dates</button>
  </form>
</template>

<script>
export default {
  name: "baseInput",
  data:() => ({
    theDate: '',
  }),
  methods:{
    getDate(){
      this.$emit('addDate', this.theDate)
    }
  }
}
</script>
<style>

</style>
<template>
  <form class="baseInput" @submit.prevent="">
      <label for="input">Enter your dates</label>
      <input class="baseInput__input" type="text" name="input" id="input" v-model="theDate">
      <button class="baseInput__button" @click='getDate'>Show dates</button>
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
<style lang="scss">
.baseInput{
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 50%;

  &__input{
    background: none;
    border: none;
    border-bottom: 1px solid black;
  }

  &__button{
    margin-top: 10px;
    width: 150px;
    padding: 10px 15px;
    border: none;
    border-radius: 5px;
    background-color: #3ddc97;
    color: white;
  }
}
</style>
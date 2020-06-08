<template>
  <div class="home">
    <h1 class="home__title">History Facts</h1>
    <BaseInput @addDate="createEvent"/>
    <ul>
      <li class="home__date" v-for="(fact, i) in facts.Events" :key="i">
        <p>{{ fact.text }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import BaseInput from '@/components/BaseInput.vue'

export default {
  name: 'Home',
  components: {
    BaseInput,
  },
  data:() => ({
    facts: {},
    month: 6,
    day: 14,
  }),
  methods:{
    createEvent(e){
      let dates = e.split('/');
      console.log(e)
      this.month = dates[0];
      this.day = dates[1];
      this.fetchData()
    },
    fetchData(){
    // eslint-disable-next-line
    historyData.load(
    {
    month: this.month,
    day: this.day,
    callback: data => {
      this.facts = data;
      },
    })
    }
  }
}
</script>

<style lang="scss">
.home{
  &__date{
    list-style: none;
    border-radius: 5px;
    box-shadow: 10px 5px 5px;
  }
}
</style>
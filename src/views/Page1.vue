<template>
  <div class="fact">
    <h1 class="fact__title">History Facts</h1>
    <BaseInput @addDate="createEvent"/>
    <ul class="fact__content">
      <li class="fact__date" v-for="(fact, i) in facts.Events" :key="i">
        <p>{{ fact.text }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import BaseInput from '@/components/BaseInput.vue'

export default {
  name: 'fact',
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
.fact{
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
  &__content{
    align-items: center;
    display: flex;
    flex-direction: column;
  }
  &__date{
    list-style: none;
    padding: 20px;
    margin-bottom: 10px;
    width: 50%;
    height: auto;
    box-shadow: 9px 9px 5px -7px rgba(0,0,0,0.75);
    transition: scale 0.3s ease;

    &:hover{
      transform: scale(1.05);
      box-shadow: 10px 10px 18px -11px rgba(0,0,0,0.75);
    }
  }
}
</style>
<template>
  <div id="app">
    <section> 
      <h2>Как зовут твоих друзей?</h2>
      <input type="checkbox" id="jack" value="Джек" v-model="checkedNames">
      <label for="jack">Джек</label>
      <input type="checkbox" id="john" value="Джон" v-model="checkedNames">
      <label for="john">Джон</label>
      <input type="checkbox" id="mike" value="Майк" v-model="checkedNames">
      <label for="mike">Майк</label>
      <p>Выбрано: {{checkedNames}}</p>
      <br>
    </section>

    <section>
      <h2>Сколько у тебя домашних питомцев?</h2>
      <input type="radio" id="one" value="Один" v-model="picked">
      <label for="one">Один</label>
      <br>
      <input type="radio" id="two" value="Два" v-model="picked">
      <label for="two">Два</label>
      <br>
      <input type="radio" id="three" value="Три" v-model="picked">
      <label for="three">Три</label>
      <span>Выбрано: {{ picked }}</span>
      <br>
      <br>
    </section>
    <section>
      <h2>Какой твой любимый?</h2>
      <select v-model="selected">
        <option disabled value="">Выберите один из вариантов</option>
        <option>А</option>
        <option>Б</option>
        <option>В</option>
      </select>
      <br>
      <br>
      <span>Выбрано: {{ selected }}</span>
      <br>
    <br>
</section>

<h2>Как зовут твоего питомца?</h2>
<select name="" id="" v-model="selecteded">
  <option :value="name.value"
  v-for="name in names">
    {{ name.text }}
  </option>
</select>
<br>
<span>Выбрано: {{selecteded}}</span>
<br>
<br>
<input
  type="checkbox"
  v-model="toggle"
  true-value="да"
  false-value="нет"
>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      checkedNames: [],
      picked: [],
      selected: '',
      selecteded: '',
      names: [
        {text: 'Anna', value: '0'},
        {text: 'Baxik', value: '1'},
        {text: 'Misha', value: '2'},
        {text: 'Egor', value: '3'}
      ]
    }
  },
  methods: {
    addStudent() {
      const studentsId = `${this.name}${Math.round(Math.random()*1000)}`;
      this.students.push({name: this.name, id: this.name});
    },
    deleteStudent(index) {
      this.students.splice(index, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px 50px;
}
</style>

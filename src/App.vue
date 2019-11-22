<template>
  <div>
    Firstname <input type="text" v-model="Firstname">
    <br>
    Lastname <input type="text" v-model="Lastname">
    <br>
    <button @click="addNew()">Add</button>
  <ul>
    <li v-for="element in numbers">{{ element }}</li>
  </ul>
    


  </div>
</template>

<script>
export default {
        data() {
            return {numbers: []}
        },
        methods: {
            addNew() {
              
                this.numbers.push(this.Firstname+' '+this.Lastname)
              }
            }
        };

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app > ul
{
  list-style-type: none;
}
</style>

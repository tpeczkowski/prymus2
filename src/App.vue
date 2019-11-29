<template>
  <div id="app">
    <div>
      <div v-if="participants.length > 0">
        <h1>Participants list</h1>
        <participants-list :list="participants"></participants-list>
      </div>
    </div>
    
    <h3>New participant</h3>
    <new-participant-form @added="addNewParticipant($event)"></new-participant-form>
  </div>
</template>

<script>
  import ParticipantsList from "./ParticipantsList.vue";
  import NewParticipantForm from "./NewParticipantForm.vue";

  export default {
    components: {ParticipantsList, NewParticipantForm},
    data() {
      return {
        newParticipant: {firstname: '', lastname: ''},
        
        participants: [],
      };
    },
    methods: {
      addNewParticipant(newParticipant) {
        if (!newParticipant.lastname) {
          return;
        }
        this.participants.push(newParticipant);
        this.newParticipant = {};
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

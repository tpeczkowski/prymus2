<template>
  <div style="width: 400px; margin-right: auto;
  margin-left: auto">
    <form class="form-group" @submit.prevent="add()">
      <label for="formGroupExampleInput">Firstname</label>
      <input type="text" class="form-control" id="formGroupExampleInput" v-model="newParticipant.firstname">
      <br>
      <label for="formGroupExampleInput">Lastname</label>
      <input type="text" class="form-control" id="formGroupExampleInput" v-model="newParticipant.lastname">
      <br>
      <button class="btn btn-primary">Add new participant</button>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {newParticipant: {}};
    },
    methods: {
      add() {
        this.$emit('added', this.newParticipant);
        this.newParticipant = {};
      }
    }
  };
</script>
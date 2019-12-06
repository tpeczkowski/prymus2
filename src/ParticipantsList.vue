<template>
  <div>
    <ol>
        <li v-for="(person, index) in list">
            {{ person.firstname }}
            {{ person.lastname }}
            <button class="btn btn-danger" @click="remove(index)">Remove</button>
        </li>
    </ol>
  </div>
</template>

<script>
  export default {
    data() {
      return {
      newParticipant: {},
      participants: []
      }
    },
    props: ['list'],
    methods: {
      remove (index) {
        this.$delete(this.list, index)
      }   
    }
  };
</script>
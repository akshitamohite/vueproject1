
<template>
  <h1>vue learn : {{ name }}</h1>
  <p v-if="status === 'active'">user is active</p>
  <p v-else-if="status === 'pending'">user is pending</p>
  <p v-else>user is inactive</p>

  <h3>TASKS</h3>
  <ul>
    <li v-for="task in list" :key="task">
      {{ task }}
    </li>
  </ul>

  <!-- <a v-bind:href="link">click for youtube</a> -->
  <a :href="link">click for youtube</a>
  <br>
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>


</template>

<script>
export default {
  data() {
    return {
      name: 'maya',
      status: 'active',
      list: ['task1', 'task2', 'task3'],
      link: 'https://youtube.com'
    };
  },
  methods: {
    toggleStatus() {
      if(this.status === 'active') { this.status = 'pending'; }
      else if(this.status === 'pending') {this.status = 'inactive'; }
      else { this.status = 'active'; }
    }
  }
};
</script>
<script setup>
  import { Authenticator } from '@aws-amplify/ui-vue';
  import '@aws-amplify/ui-vue/styles.css';
</script>
<template>
  <authenticator>
    <template v-slot="{ user, signOut }">
      <h1>Hello {{ user.username }}! 1111</h1>
      <button @click="signOut">Sign Out</button>
    </template>
  </authenticator>
</template>

<!-- <script>
  import { API } from 'aws-amplify';
  import { createTodo } from './graphql/mutations';
  import { listTodos } from './graphql/queries';
  import { onCreateTodo } from './graphql/subscriptions';

  export default {
    name: 'App',
    async created() {
      this.getTodos();
      this.subscribe();
    },
    data() {
      return {
        name: '',
        description: '',
        todos: []
      };
    },
    methods: {
      async createTodo() {
        const { name, description } = this;
        if (!name || !description) return;
        const todo = { name, description };
        this.todos = [...this.todos, todo];
        await API.graphql({
          query: createTodo,
          variables: { input: todo }
        });
        this.name = '';
        this.description = '';
      },
      async getTodos() {
        const todos = await API.graphql({
          query: listTodos
        });
        this.todos = todos.data.listTodos.items;
      }
      , subscribe() {
        API.graphql({ query: onCreateTodo }).subscribe({
          next: (eventData) => {
            let todo = eventData.value.data.onCreateTodo;
            if (this.todos.some((item) => item.name === todo.name)) return; // remove duplications
            this.todos = [...this.todos, todo];
          }
        });
      }
    }
  };
</script> -->
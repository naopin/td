<template>
    <div id="app">
      <h1>ToDoList</h1>
      <label v-for="label in options" :key="label">
        <input type="radio">{{ label.label }}
      </label>
        <table>
        <thead>
          <tr>
            <th class="id">ID</th>
            <th class="comment">コメント</th>
            <th class="state">状態</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in todos" :key="item">
            <!-- <td>{{ item.id }}</td> -->
            <td>{{item.title}}</td>
          </tr>
        </tbody>
      </table>
        <h2>新規タスクの追加</h2>
      <form>
        <input type="text" v-model="newTodo">
        <button v-on:click="addTodo">追加</button>
      </form>
    </div>
</template>

<script>
export default {
  name: '#app',
  data() {
     return {
         options: [
           {label: 'すべて' },
           {label: '作業中' },
           {label: '完了' }
         ],
         todos: [
           {title :'Test'},
         ],
         newTodo: null,
    };
  },
  methods: {
    addTodo() {
      this.todos.push({title :this.newTodo})
    }
  }
};
</script>
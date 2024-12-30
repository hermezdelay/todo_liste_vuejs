<script setup>
</script>

<template>
    <div>This is your Todo liste</div>
    <form action="" @submit.prevent="ajouter_element">
      <fieldset role="group">
        <input type="text" placeholder="tappez votre todo ici !" v-model="newtodo">
        <button :disabled="newtodo.length == 0">Ajouter</button>
      </fieldset>
    </form>
      <div v-if="todos.length === 0"> Vous n'avez pas de tàches à faire :( </div>
      <div v-else>
        <ul>
          <li 
          v-for="todo in todos"
          :key="todo.date"
          :class="{completed :  todo.completed}"
          > 
            <label for="">
              <input type="checkbox" v-model="todo.completed">
              {{ todo.title }}
            </label>
            </input>
          </li>
        </ul>
      </div>
</template>
<script setup>
import { ref } from 'vue'

//const todos = ref([])
const todos = ref([ {
  title : 'tache de test',
  completed : true,
  date : 1
  }, {
  title : 'tache à faire ',
  completed : false,
  date : 2
  }
])

const newtodo = ref("")

const ajouter_element = () => {
  todos.value.push({
    title : newtodo.value,
    completed : false,
    date : Date.now(),
  })
  newtodo.value=""
}

</script>

<style>
.completed {
  opacity: 0.5;
  text-decoration: line-through;
}


</style>
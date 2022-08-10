<script setup>
import InputBox from "input-box";
import NoteList from "note-list";
import { ref } from "vue";

const text = ref("");
const todos = ref([]);

function addTodo() {
  todos.value.push(text.value);
  text.value = "";
}
</script>

<template>
  <main>
    <InputBox v-model="text" @keydown.enter="addTodo"></InputBox>
    <button @click="addTodo">Add</button>
    <NoteList :todos="todos"></NoteList>
  </main>
</template>

<style scoped>
main {
  padding-bottom: 50vh;
}
</style>

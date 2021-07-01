<template>
  <div class="hello text-center">
    <h1
      class="bg-primary"
      style="margin: 20px 450px 20px 450px; border-radius: 15px"
    >
      {{ msg }}
    </h1>
    <div class="add">
      <button @keypress.shift="addTask" @click="addTask" class="addList btn">
        +
      </button>
      <input
        id="input"
        v-bind:value="inputValue"
        class="mt-4"
        type="text"
        v-bind:placeholder="placeHolder"
        @input="inputHandler"
      />
    </div>
    <div class="lists">
      <ul>
        <li v-for="(list, i) of notes" :key="list">
          ({{ i + 1 }}) {{ list }}
          <button class="btn del btn-danger" v-on:click="deleteTask">
            Удалить
          </button>
        </li>
      </ul>
    </div>
    <div class="demand" v-if="notes.length === 0">
      Добавьте свою первую заметку
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      placeHolder: "Добавить задачу",
      inputValue: "",
      notes: ["9:30 начало учебы", "19:00 начало футбола"],
    };
  },
  methods: {
    inputHandler(event) {
      this.inputValue = event.target.value;
    },
    addTask() {
      if (this.inputValue === "") {
        alert("Поля не должно быть пустым");
      } else {
        this.notes.push(this.inputValue);
        this.inputValue = "";
      }
    },
    deleteTask(idx) {
      this.notes.splice(idx, 1);
    },
    keyEnter(e) {
      if (e.key === "Enter") {
        this.addTask();
      }
    },
  },
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
  list-style: none;
  line-height: 50px;
}
.del {
  float: right;
  margin-right: 22rem;
}
input {
  padding: 10px;
  width: 35rem;
  border-radius: 5px;
  outline: none;
  border: none;
}
.addList {
  background: transparent;
  font-size: 40px;
  color: rgb(229, 235, 235);
}
.addList:hover {
  transition: 0.7s;
  color: aquamarine;
}
</style>

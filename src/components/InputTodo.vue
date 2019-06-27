<template>
    <section class="toDoSection">
      <div class="toDoDiv">
        <input 
          class="toDoInput"
          v-model="selectedToDo"
          placeholder="Saisissez une todo..." 
          v-on:keyup.enter="addToDo"
        >
        <button
          class="toDoButton"
          v-on:click="addToDo"
        > +
        </button>
      </div>
    </section>
</template>

<script>
    export default {
        name: "InputTodo",
        data() {
            return {
                selectedToDo: ''
            }
        },
        methods: {
            addToDo() {
                if (this.selectedToDo !== '') {
                    this.$emit('add-todo', this.selectedToDo);
                    this.selectedToDo = "";
                }
            }
        }
    }
</script>

<style>
    .toDoSection {
        padding-top: 50px;
        padding-bottom: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .toDoDiv {
        padding: 10px;
        border: 1px solid grey;
        border-radius: 5px;
        width: 25%;
        display: flex;
        justify-content: space-between;
    }

    .toDoInput {
        border: 0;
        border-bottom: 1px solid transparent;
        transition: all .2s;
        outline: none;
        padding: 3px 0;
    }

    .toDoInput:focus {
        border-bottom-color: grey;
    }

    .toDoButton {
        background: none;
        border: 1px solid grey;
        width: 25px;
        height: 25px;
        font-size: 1rem;
        cursor: pointer;
        margin-left: 10px;
        border-radius: 50%;
        outline: none;
        color: grey;
        transition: all 0.2s ease;
    }

    .toDoButton:hover {
        transform: scale(1.1);
    }
</style>


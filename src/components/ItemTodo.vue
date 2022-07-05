<template>
    <section class="toDoItemSection">
      <div class="toDoItemDiv">
        <p class="toDoText"> 
          {{ dateFormat }} : {{ todo }}
        </p>
        <button 
          class="toDoItemButton"
          v-on:click="removeToDo"
        > -
        </button>
      </div>
    </section>
</template>

<script>
    const dateFormatter = new Intl.DateTimeFormat('en-US');

    export default {
        name: "ItemTodo",
        props: {
            date: Date,
            todo: String
        },
        computed: {
            dateFormat() {
                return dateFormatter.format(this.date);
            }
        },
        methods: {
            removeToDo() {
                this.$emit('remove-todo');
            }
        },
    }
</script>

<style>
    .toDoItemSection {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .toDoItemDiv {
        border: 1px solid grey;
        border-radius: 5px;
        padding: 10px;
        margin-bottom: 15px;
        width: 25%;
        display: flex;
        justify-content: space-between;
    }

    .toDoItemButton {
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

    .toDoItemButton:hover {
        transform: scale(1.1);
    }

    .toDoText {
        margin: 0;
        padding: 0;
        color: grey;
    }
</style>
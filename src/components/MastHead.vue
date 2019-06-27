<template>
    <header class="mast-head">
      <h1> 
        {{ title }}
      </h1>
    </header>
</template>

<script>
    export default {
        name: "MastHead",
        data() {
            return {
                title: 'Todo-app',
            }
        }
    }
</script>

<style>
    .mast-head {
        background-color: black;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .mast-head h1 {
        margin: 5px;
        text-align: center;
    }
</style>


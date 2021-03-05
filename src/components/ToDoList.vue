<!--Partie j'ai attribué le mot underline pour les tache barré et delet task pour les taches qui existe déja et on veut les supprimer apres -->
<template>
<ul>
    <li class="list" v-bind:class="{'taskDone':task.checked}" v-for="(task, index) in tasks" :key="(task, index)">
        <input v-on:click="underline(index)" type="checkbox"/>
        {{task.description}}
        <button v-on:click="deleteTask(index)" class="delete is-medium"></button>
        <li>
 </ul>
</template>

<!--Partie ou on supprime et souligne les taches effectuer et existante -->
<script>
export default {
 name: "ToDoList",
  props: ["tasks"],

  methods: {
    deletetask(index) {
      this.$emit('delete', index) 
      },
      underline(index){
          this.$emit('underline' , index)
      }
  }
}
</script>

<!--Partie du style pour la liste des taches -->
<style  scoped>
.List{
    display: flex;
    justify-content: space-around;
    margin-bottom: 1%;
}
</style>
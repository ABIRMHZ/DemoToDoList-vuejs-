<!-- Vuejs TODOLIST Projet réaliser par Abir Mharzi pour ce projet j'ai opté 
une méthode plutot differente j'ai eu des defficulté niveau d'affichage du scripte j'espere 
que mon code et bien ce que on est demandé a faire  -->
<template>
    <input v-model="task" id="input" class="input" type="text" placeholder="addtask">
    <span v-on:click="addTask" ></span>
</template>
<!--Partie style des input et div-->
<style scoped>
    input{
        width: 30%;
        margin: 2%;
    }
    div{
        margin-top: 2.5%;
    }
</style>

<!--Partie script -->
<script>
export default {
    name: 'ToDoinput',
    data(){
      return {
          task: " "
          }
    },
    methods: {
        addTask(){
           this.$emit('newTask', this.task)
           document.getElementById("input").value = "";
        }
    }
}
</script>
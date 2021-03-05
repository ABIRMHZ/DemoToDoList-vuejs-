<!--Partie ToDo-->
<template>
<section class="ToDo">
    <nav>
        <h1>{{ date }}</h1>
        <h1 class="ToDoDemo"> Demo TodoList </h1>
        <h1>{{tasks.lenght}} Taches</h1>
    </nav>
    <to-do-input @newtask="showtask"></to-do-input>
    <to-do-list @deletetask="hidetask" @underline="taskDone" :tasks="tasks"></to-do-list>
</template>

<!--Partie afficahge de la date stocké dans la méthode computed et les methodes pour afficher supprimer et souligner les taches-->
<script>
import ToDoInput from './ToDoInput.vue';
import ToDoList from './ToDoList.vue';
export default {
  components: { ToDoInput, ToDoList },
data() {

        return {
            day: ["Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi", "Dimanche"],
            month: ["Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"],
            tasks: [],
        }

    },
    computed: {

        date: function() {
            let today = new Date();
            let todate = `${this.day[(today.getDate())-1]}` + ' ' + today.getDay() + ' ' + `${this.month[(today.getMonth())]}` + ' ' + today.getFullYear()
            return todate
        }

    },
    
    methods: {
        showtask(task){
            this.tasks.push({description: tasks, cheked:false})
        },
        hidetask(hide){
            this.task.splice(hide,1)
        },
        underline(taskDone){
            this.tasks.check(taskDone)
        }
    }
}
</script>

<!--Partie du style-->
<style  scoped>
nav{
display: flex;
justify-content: space-around;
box-shadow: 0px 2px 6px gray;
}
.ToDo{
background-color: white;
border-radius: 5px;
box-shadow: 5px 5px 20px gray;
}
h1{
font-size: 1.5em;
}
.ToDoDemo{
color: violet;
}
</style>
<template>
<div class="container">
  <h2 class="text-center mt-5">My Vue App</h2>
<div class="d-flex">
<input v-model="task" type="text" placeholder="enter task" class="form-control">
<button @click="submitTask" class="btn btn-warning rounded-0">submit</button>
</div>
<table class="table mt-5">
  <thead>
    <tr>
      <th scope="col">Task</th>
      <th scope="col">Status</th>
      <th scope="col">#</th>
      <th scope="col">#</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task,index) in tasks" :key= "index">
      <th>{{task.name}}</th>
      <td>{{ task.status }}</td>
      <td><div class="text-center" @click="editTask(index)">
      <span class="fa fa-pen" ></span>
      </div></td>
      <td>
      <div class="text-center" @click="deleteTask(index) ">
      <span class="fa fa-trash" ></span>
      </div>
    </td>
    </tr>

  </tbody>
</table>
</div>

</template>

<script>


export default {
  name: 'TodoApp',
  props: {
    msg: String
  },
  data(){
    return{
      task:'',
      editedTask:null,
      tasks:[
        {
        name:'Buy bananas',
        status:'to-do'
        },
        {
        name:'Buy apple',
        status:'in-progress'
        },
      ]
    }
  },
methods: {
  submitTask(){
if(this.task.length===0) return;
if(this.editedTask===null){
  this.tasks.push(
    {
      name:this.task,
      status:'todo'
    }
  );
  }else{
    this.tasks[this.editedTask].name=this.task;
    this.editedTask=null;
  }
this.tasks.push({
  name:this.task,
  status:'to-do'
}),
this.task='';
  },
deleteTask(index){
  this.tasks.splice(index,1);
},
editTask(index){
this.task=this.tasks[index].name;
this.editedTask=index;
}
}
};
</script >
<style scope></style>


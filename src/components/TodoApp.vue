<template>
<div class="container">
  <h2 class="text-center mt-5">My Vue App</h2>
<div class="d-flex">
<input type="text" placeholder="enter task" class="form-control">
<button class="btn btn-warning rounded-0">submit</button>
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
    <tr>
      <th>Buy bananas</th>
      <td>To-do

      </td>
      <td><div>
      <span class="fa fa-pen" ></span>
      </div></td>
      <td>
      <div>
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
  }
}
</script >
<style scope></style>


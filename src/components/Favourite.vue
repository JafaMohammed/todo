<template>
  <div class="favourite">
    <div class="row">
      <div class="col-1 col-md-1 col-lg-2"></div>

      <div class="col-10 col-md-9 col-lg-7">
        <div id="favourite">
          <p>
            <b>Favourite</b>
          </p>
        </div>

        <div
          class="card bg-light"
          style="margin-bottom:10px;"
          v-for="todo in todos.slice().reverse()"
          value="todo.favourite"
          :key="todo.id"
        >
          <div class="row" style="padding:8px;">
            <div class="col-8 col-md-10 col-lg-10">
              <span style="float:left;">{{ todo.title }}</span>
            </div>
            <div class="col-4 offset-0 col-md-2 offset-md-0 col-lg-2 offset-lg-0">
                <span id="clickableAwesomeFont">
              <i class="fa fa-star" v-on:click="unStar(todo)"></i>
              </span>&nbsp;&nbsp;&nbsp;
                <span id="clickableAwesomeFont">
              <i class="fa fa-trash" v-on:click="removeTodo(todo)"></i>
                </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TasksList",
  data: function() {
    return {
        // eslint-disable-next-line no-undef
      todos: todoStorage.fetch()
    };
  },
  methods: {
    removeTodo: function(todo) {
      this.todos.splice(this.todos.indexOf(todo), 1);
    }
  }
};
</script>

<style scoped>
#tasks {
  color: #fff;
  font-size: 16px;
}
p {
  text-align: left;
  font-weight: 350;
  font-family: "Raleway", sans-serif;
}
h5 {
  text-align: left;
  font-size: 17px;
  justify-content: space-around;
}
.card {
  background-color: #fff;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  font-size: 20px;
  min-height: 50px;
  text-align: left;
}
</style>
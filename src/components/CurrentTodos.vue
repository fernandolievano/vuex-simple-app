<template>
    <div class="row justify-content-center align-items-center" id="current-todos">
        <div class="col-sm-3 col-xs-12">
            <h3 v-if="todos.length > 0"> Current <span class="badge badge-primary" v-text="todos.length"></span> </h3>
        </div>
        <div class="col-sm-9 col-xs-12">
            <ul class="list-group">
                <li class="list-group-item" v-for="todo in todos" :key="todo.key">
                    {{ todo.body }}
                    <div class="btn-group">
                        <button type="button" @click="edit(todo)" class="btn btn-default btn-sm">
                            Edit <i class="icon ion-md-create"></i>
                        </button>
                        <button type="button" @click="complete(todo)" class="btn btn-default btn-sm">
                            Complete
                            <i class="icon ion-md-checkmark"></i>
                        </button>
                        <button type="button" @click="remove(todo)" class="btn btn-default btn-sm text-danger">
                            Remove
                            <i class="icon ion-md-trash"></i>
                        </button>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  methods: {
    edit (todo) {
      this.$store.dispatch('editTodo', todo)
    },
    complete (todo) {
      this.$store.dispatch('completeTodo', todo)
    },
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  },
  computed: {
    todos () {
      return this.$store.getters.todos
    }
  }
}
</script>

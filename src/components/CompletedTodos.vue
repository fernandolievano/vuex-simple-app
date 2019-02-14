<template>
    <div class="row justify-content-center align-items-center" id="completed-todos">
        <div class="col-sm-3 col-xs-12">
            <h3 v-if="completed.length > 0"> Completed <span class="badge badge-success" v-text="completed.length"></span> </h3>
        </div>
        <div class="col-sm-9 col-xs-12">
            <ul class="list-group">
                <li class="list-group-item" v-for="todo in completed" :key="todo.key">
                    <div class="row">
                        <div class="col-sm-9 col-xs-8">
                            {{ todo.body }}
                        </div>
                        <div class="col-sm-3 col-xs-4">
                            <div class="btn-group">
                                <button type="button" @click="remove(todo)" class="btn btn-sm text-danger">
                                    Remove <i class="icon ion-md-trash"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  methods: {
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  },
  computed: {
    completed () {
      return this.$store.getters.completedTodos
    }
  }
}
</script>

<template>
    <div id="get-todo" class="row align-items-center justify-content-center">
        <div class="col-xl-12 col-xs-12">
          <div class="row justify-content-center">
            <div class="col-sm-10 col-xs-12">
              <input class="form-control"
               :value="newTodo"
               @change="getTodo"
               placeholder="I need to...">
            </div>
            <div class="col-sm-2 col-xs-12">
              <div class="button-group">
                <button class="btn btn-outline-dark btn-block" @click="addTodo">
                  Add
                  <i class="icon ion-md-add"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
    </div>
</template>
<script>
export default{
  methods: {
    getTodo (e) {
      this.$store.dispatch('getTodo', e.target.value)
    },
    addTodo () {
      this.$store.dispatch('addTodo')
      this.$store.dispatch('clearTodo')
    }
  },
  computed: {
    newTodo () {
      return this.$store.getters.newTodo
    }
  }
}
</script>

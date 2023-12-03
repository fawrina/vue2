<template> 
  <form @submit.prevent="onSubmit"> 
    <h2 class="label-wrapper"> 
      <label for="new-todo-input" class="labellg"> 
        Что нужно сделать? 
      </label> 
    </h2> 
    <input 
      type="text" 
      id="new-todo-input" 
      name="new-todo" 
      autocomplete="off" 
      v-model.lazy.trim="label" 
      class="inputlg" /> 
    <button type="submit" class="btn btnprimary btnlg">Добавить</button> 
    <h2>Поиск</h2> 
    <input type="text" id="search-todo-input" v-model="searchQuery" @input="onSearch" /> 
  </form> 
</template> 
 
<script> 
export default { 
  methods: { 
    onSubmit() { 
      if (this.label === "") { 
        return; 
      } 
      this.$emit("todo-added", this.label); 
      this.label = ""; 
    }, 
    onSearch() {
      this.$emit("search-todo", this.searchQuery);
    }
  }, 
  data() { 
    return { 
      label: "", 
      searchQuery: "",
    }; 
  }, 
}; 
</script>
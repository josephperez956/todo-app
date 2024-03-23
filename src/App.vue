<script>
import {ref} from 'vue'
const name = ref('')
const todoList = ref([])
const inputContent = ref('')
const inputCategory = ref(null)
const addTodoList = () => {
     if(inputContent.value.trim()==='' || inputCategory.value == null) {
          return
     }
     todoList.value.push({
          content: inputContent.value,
          category: inputCategory = n,
     })
     inputContent.value = ''
     inputCategory.value = ''
     console.log(todoList)
}
</script>

<template>
     <main class="app">
          <section class="greeting">
               <h2 class="title">
                    What's up, <input type="text" placeholder="Enter Name" v-model="name" />
                    {{ name }}
               </h2>
          </section>
          <section class="create-todo">
               <h3>CREATE A TO DO LIST</h3>
               <form @submit.prevent="addTodoList">
                    <h4>What's on your to do list?</h4>
                    <input type="text" placeholder="e.g. Make a Video" v-model="inputContent" />
                    {{  inputContent }}

                    <h4>Pick a Category</h4>
                    <div class="options">
                         <label>
                              <input type = "radio" name="category" value="business" v-model="inputCategory" />
                              <span class="bubble business"></span>
                              <div>Business</div>
                         </label>

                         <label>
                              <input type = "radio" name="category" value="personal" v-model="inputCategory" />
                              <span class="bubble personal"></span>
                              <div>Personal</div>
                         </label>

                         {{ inputCategory }}
                    </div>
               </form>
          </section>
          <section class="todo-list">

          </section>
     </main>
</template>


<template>
  <div>
    <div class="forms">
        <b-form-input
            class="input"
            v-model="title" 
            type="text" 
            placeholder="Enter the title of Todo" 
            @change="handleChange" 
            v-bind:value="title"
    ></b-form-input>
        <b-button 
            :variant=" this.title.length <5 ? 'danger' : 'success' "
            @click.prevent="handleClick"
        >addTodo</b-button>
    </div>
    
    <ul>
        <li
        v-for="todo in todos" 
        :key="todo.id"
        >{{todo.title}}
        <b-button 
            class="del"
            variant="danger"
            @click.prevent="handleDelete(todo.id)"
            
        >X</b-button>
        </li>
    </ul>
  </div> 
</template>

<script>
  export default {
      name: "Test",
      data(){
          return{
              title:'',
              todos: [
                  {
id:1, title: "Plan for a training activity"
                  },
                  {
id:2, title: "Meeting"
                  }
              ]
            
          }
      },
      methods:{
handleChange(event) {
        this.title= (event.target.value).trim()
        
},
handleClick() {
    if(this.title.length< 5){
alert('saisir un titre')
    }
    else{
        const newTodo= {id: Math.random(), title: this.title}
    this.todos= [...this.todos, newTodo]
    this.title=''
    this.isActive= false
    
      }
    },

    handleDelete(id) {
    this.todos = this.todos.filter(todo => todo.id !== id);
    }
    
  }
  
  }
  

</script>



<style scoped>
  ul {
    list-style-type: none;
    margin: 0px;
    padding: 0px
}
li {
    display: flex;
    justify-content: space-between;
    margin: 10px 50px;
    padding: 5px;
    border: 1px solid gray; 
    border-radius: 5px
}
.forms {
    display: flex;
    margin-left: auto;
    margin-right: auto; 
    margin-top: 30px;
    margin-bottom: 30px;
    width: 50%;
    /* margin: 30px 0px */
    }
.input {
    margin: 0px 10px;
    
}


</style>
<template>
  <ul>
    
    
    <!--
      <PresonComponent
      v-for="(item, index) in employees"

      :key="index"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :id="item.id"
      :isvisible="item.isvisible"
      @showEMP="togggleShow"       
      @delete="remove"
      />
            
       @show = ตั้งขึ้นมาเอง  -->
  </ul>
</template>

<script>
//import PresonComponent from './PresonComponent.vue'

export default {
  name: 'ListPreson',


  components: {
   // PresonComponent,
  },
  /*
  methods:{
    togggleShow(id){
      this.employees = this.employees.map((item)=>{
        if(item.id === id){
          return {...item,isvisible:!item.isvisible}
        }
        return item
      })
    },
    remove(id){
      this.employees = this.employees.filter(item=>{
        return item.id !== id
      })
    },
  },
  data() {
    return {
      employees: [
        { id:1, name: 'zone', salary: 30000, department: "Programer",isvisible: false},
        { id:2, name: 'ztwo', salary: 20000, department: "Markgeting",isvisible: false },
        { id:3, name: 'zthree', salary: 34000, department: "Programer",isvisible: false },
        { id:4, name: 'zfore', salary: 20780, department: "Grappic",isvisible: false },
        { id:5, name: 'zxc', salary: 1234, department: "Programer",isvisible: false }
      ]
    }
  }
  */
}
</script>

<style scoped>
  ul{
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
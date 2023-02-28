<template>
  <header>
    <h1>ระบบจัดการข้อมูล</h1>
  </header>
  <FromComponent @save="insertEmployee"/>
  <section class="employee-content">
  <h2>ข้อมูลพนักงาน</h2>
  <ListPreson/>
  
  </section>
</template>

<script>
import FromComponent from '../components/FromComponent.vue';
import ListPreson from '../components/ListPreson.vue'

export default {
  name:"HomeView",
  components:{
    ListPreson,
    FromComponent
},
  data(){
    return{
      employees:[]
    }
  },
  methods:{
      insertEmployee(data){
        //console.log("ads", data)
        this.employees.push(data);
      }
  },
  
}
</script>



<style>
  *{
    box-sizing: border-box;
  }
  body{
    margin:0;
  }
  header{
    margin: 3rem;
    box-shadow: 0 2px 8px black;
    border-radius:10px;
    padding: 1rem;
    background-color: orange;
    color: green;
    text-align: center;

  }
  .employee-content{
    box-shadow: 0 2px 8px black;
    margin: 3rem;
    border-radius:10px;
    padding: 1rem;
    text-align: center;


  }
  .employee-content h2{
    font-size: 2rem;
    border-bottom: 4px solid #ccc;
    color: purple;
    margin: 0 0 0.5rem 0;

  }
</style>
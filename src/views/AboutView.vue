<template>
  <div class="about">

    <section>
    <from>
      <label>ชื่อ : </label>
      <input type="text" ref="nickNameEL"/>


      <button @click="sub">save</button>
    </from>


    <h1>{{ firstName }}</h1>
    <h1>{{ getFullName }}</h1>
    <h2>{{ age }} + 2 = {{ age + 2}}</h2>
    <h2>method : {{ getRandomByMethod() }}</h2>
    <h2>method2 : {{ getRandomByMethod() }}</h2>
    
    <hr>
    <h2>computed : {{ getRandomByComputed }}</h2>
    <h2>computed2 : {{ getRandomByComputed }}</h2>

    <h1>เงินเดือน : {{ salary }}</h1>
    <h1>เงินต่อปี : {{ getIncome }}</h1>
    <h1>ตำแหน่งงาน : {{ getDepartment }}</h1>
    <button @click="addSalary(5000)">เพิ่มเงินเดือน</button>
    <h2>number <span v-html="address"></span></h2>
    {{ isVisible }}<button @click="visible">{{ isVisible ? "ซ่อน":"แสดง"}}detail</button>

    <article v-show="isVisible">
      <h2 v-if="array.length === 0">ไม่มีงานอดิเรก</h2>
    <div v-else>
    <h2>งานอดิเรก</h2>
    <ul>
      <li v-for="(item,index) in array" :key="index">{{ index }} - {{ item }}</li>

    </ul>
    </div>

    <h2>ข้อมูลพื้นฐาน</h2>
    <ul>
      <li v-for="(item,key) in general" :key="key">{{ key }} - {{ item }}</li>

    </ul>
    </article>



    <!-- ใส่ v-bind กับไม่ใส่ มีค่าเท่ากัน -->
    <img :src="picture" v-bind:width="width" :height="height" ref="imageURL"/> 
    <br>
    
    <h1>dsa {{ nickName }}</h1>
    <br><br>

    <a :href="link" target="_blank">link</a>
    <br>
    <button @click="showData">show</button>
    <button @click="increment(10)">เพิ่ม</button>
    <!-- right= ขวา midden=กลาง ctrl=ต้องกดCtrl+คลิกเมาท์ช้าย-->
    <button @click.right="decrement(5)">ลด</button>

    </section>
  </div>
</template>


<script>
export default {
  name: 'app',
  data(){
    return{
      firstName:"z",
      lastName: "one",
      nickName: "",
      age:15,
      address:"<i>1233212312132</i>", //i = ตัวเอียง
      picture: "https://m.media-amazon.com/images/I/51T9B5HKY4L._AC_UF894,1000_QL80_.jpg",
      height: 100,
      width: 70,
      link: "https://m.media-amazon.com/images/I/51T9B5HKY4L._AC_UF894,1000_QL80_.jpg",
      array:["asd","qwe","zxc","ghj","kjh"],
      general:{ gender:"ชาย",width:50,height:170,status:true },
      isVisible:false,
      salary:12000
    }
  },
  methods: {

    showData(){
      
      alert(this.firstName)
    },
    increment(value){
      this.age+=value
    },
    decrement(value){
      this.age-=value
    },
    setNickName(event){
      this.nickName=event.target.value
    },
    sub(){

      this.nickName=this.$refs.nickNameEL.value;
    },
    visible(){
      this.isVisible = !this.isVisible
    },
    getRandomByMethod(){
      return Math.random();
    },
    addSalary(value){
      this.salary+=value
    }
  },
  computed:{
    getFullName(){
      return this.firstName + this.lastName
    },
    getRandomByComputed(){
      return Math.random();
    },
    getIncome(){
      return this.salary * 12;
    },
    getDepartment(){
      return this.salary >= 30000 ? "project manager" : "programer" 
    }
  },
  watch:{
    salary(value){ //set ให้เงินเดือนห้ามเกิน 50000
      if(value>=50000){
        alert("เงินเดือนเกินกำหนด")
        setTimeout(()=>{
          this.salary = 20000
        },2000)//รอ 2000ms แล้วเงินเดือนจะ reset
      }
    }
  }
}
</script>>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

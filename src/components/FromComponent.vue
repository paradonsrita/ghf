<template>
    <form @submit.prevent="submitForm">
        <div class="form-control">
            <label for="emp-name">ชื่อ</label>
            <input type="text" v-model.trim="employee.name"/> <!-- trim = ตัดช่องว่างซ้ายขวา -->
        </div>
        <div class="form-control">
            <label for="emp-salary">เงินเดือน</label>
            <input type="number" v-model="employee.salary"/>
        </div>
        <div class="form-control">
            <label for="emp-department">ตำแหน่ง</label>
            <select v-model="employee.department">
                <option value="ฝ่ายการตลาด">ฝ่ายการตลาด</option>
                <option valur="ฝ่ายการเงิน">ฝ่ายการเงิน</option>
                <option value="ฝ่ายขาย">ฝ่ายขาย</option>

            </select>
        </div>
        <div class="form-control">
            <h2>เพศ</h2>
            <div>
                <input type="radio" value="ชาย" v-model="employee.gender"/>
                <label for="gender-name" >ชาย</label>
            </div>
            <div>
                <input type="radio" value="หญิง" v-model="employee.gender"/>
                <label for="gender-name">หญิง</label>
            </div>

        </div>

        <div class="form-control">
            <h2>ทักษะภาษา</h2>
            <div>
                <input type="checkbox" value="ภาษาอังกฤษ" v-model="employee.skill"/>
                <label for="skill" >ภาษาอังกฤษ</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาจีน" v-model="employee.skill"/>
                <label for="skill" >ภาษาจีน</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาญี่ปุ่น" v-model="employee.skill"/>
                <label for="skill" >ภาษาญี่ปุ่น</label>
            </div>

        </div>
        
            <button>save</button>
        
    </form>
    {{ JSON.stringify(employee) }}
</template>
  
  <script>
  export default {
      name:"FromComponent",
      data(){
          return{
            employee:{
                name:"",
                salary:0,
                department:"ฝ่ายการตลาด",
                gender:"",
                skill:[],
            }
          }
      },
      methods:{
        submitForm(){
            this.$emit("save",this.employee);
        }
      }
  }
  </script>
  
  <style scoped>
    form{
        margin:2rem auto;
        max-width: 40rem;
        border-radius: 12px;
        box-shadow: 2px 2px rgba(0,0,0,0.25);
        padding: 2rem;
        background: #fff;
    };
    .form-control{
        margin:0.5rem 0;
    }
    label{
        font-weight: bold;
    }
    input, select{
        display:block;
        width: 100%;
        font:inherit;
        margin-top:0.5;

    }
    button{
        margin-top:1rem;
        font:inherit;
        background: palegoldenrod;
        cursor:pointer;
        padding: 0.15rem 2rem;
        border-radius: 10px;
    }
    input[type="radio"], input[type="checkbox"]{
        display: inline-block;
        width: auto;
        margin-right: 1rem;
    }
    input[type="radio"]+label, input[type="checkbox"]+label{
        font-weight: normal;
    }
    h2{
        font-size:1rem;
        margin: 0.5rem 0rem;
    }
  </style>
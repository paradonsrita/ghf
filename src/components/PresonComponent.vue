<template>
    <li>
    <h1> {{ name }} </h1>
    <button>ดูรายละเอียด</button>&nbsp;
    <button>ลบข้อมูล</button>

    <div v-show="isvisible">
    <p>เงินเดือน : {{ salary }} งาน : {{ department }}</p>
    </div>
  </li>
  </template>
  
  <script>
  export default {
      name:"PresonComponent",

      props:{
        id:{
          type:String
        },
        name: {
            type:String,
            required:true
        },
        salary:{
            type:Number,
            default:15000
        },
        department:{
          type:String,
          required:true
        },
        isvisiblr:{
          type:Boolean
        }
      }
  }
  </script>
  
  <style scoped>
  
    li{
      margin:1rem;
      font-size: 1.25rem;
      font-weight: bold;
      background: #8ddba4;
      padding: 0.5rem;
      color: #1f1f1f;
      border-radius: 25px;
    }
    button{
      font:inherit;
      cursor: pointer;
      border:1px solid #ff0077;
      background: #ff0077;
      color: white;
      padding: 0.05rem 1rem;
      box-shadow:1px 1px 2px rgba(0, 0, 0, 0.26)
    }
  </style>

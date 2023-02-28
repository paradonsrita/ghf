<template>
  <CardVue>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    
    <template v-slot:card-data>
          <p>เงินเดือน : {{ salary }} งาน : {{ department }}</p>
    </template>
  </CardVue>
</template>
  
  <script>
import CardVue from './CardVue.vue'
export default {
  name: 'PresonComponent',
  components: {
    CardVue
  },
  /*
  methods: {
    showData(id) {
      this.$emit('showEMP', id)
    },
    deleteData(id) {
      this.$emit('delete', id)
    }
  }, */
  props: {
    id: {
      type: Number
    },
    name: {
      type: String,
      required: true
    },
    salary: {
      type: Number,
      default: 15000
    },
    department: {
      type: String,
      required: true
    },
    isvisible: {
      type: Boolean
    }
  }
}
</script>
  
  <style scoped>
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

.phase-enter-from {
  opacity: 0; /* opacity = ความเข้ม */
}
.phase-enter-active {
  transition: all 0.5s linear;
}
</style>

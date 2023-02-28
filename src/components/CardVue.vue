<template>
  <li>
    <img src="https://m.media-amazon.com/images/I/51T9B5HKY4L._AC_UF894,1000_QL80_.jpg"/> 
    <hr>
    <slot name="card-header"></slot>
    <slot name="card-button"></slot>
    <slot name="card-data"></slot>
  </li>
</template>

<script>
export default {

}
</script>

<style scope>
    li{
      margin:1rem;
      font-size: 1.25rem;
      font-weight: bold;
      background: purple;
      padding: 0.5rem;
      color: #fff;
      border-radius: 25px;
    }
    img{
        width: 100px;
        height: 150px;
    }
</style>
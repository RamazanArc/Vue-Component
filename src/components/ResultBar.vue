<template>
<!--  <small class= " mt-2 d-flex justify-content-end green">{{ todoList.length }} Adet Todo Vardır</small>-->
  <small class= " mt-2 d-flex justify-content-end green">{{ itemCount }} Adet Todo Vardır</small>
</template>
<script >
export default {
  props : ["itemCount"]
}
</script>
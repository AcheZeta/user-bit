<template>
  <div class="home">
    <TableComponent />
  </div>
</template>

<script>
// @ is an alias to /src
import TableComponent from "@/components/TableComponent.vue";

export default {
  name: "home",
  components: {
    TableComponent
  }
};
</script>

<template>
  <div class="container">
    <FormComponent />
    <TableComponent />
  </div>
</template>

<script>
import FormComponent from "@/components/FormComponent.vue";
import TableComponent from "@/components/TableComponent.vue";

export default {
  name: "home",
  components: {
    TableComponent,
    FormComponent
  }
};
</script>

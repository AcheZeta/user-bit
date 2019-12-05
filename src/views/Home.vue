<template>
  <div class="home">
    <Table />
  </div>
</template>

<script>
// @ is an alias to /src
import Table from '@/components/TableComponent.vue';

export default {
  name: 'home',
  components: {
    Table,
  },
};
</script>

<template>
  <div class="home container-fluid">
    <div class="row row-cols-1 row-cols-md-4">
    <Card v-for="(memo, i) in data" v-bind:key="i" v-bind:indice="i" v-bind:numero="memo.id" v-bind:fecha="memo.fecha" v-bind:de="memo.de" v-bind:para="memo.para" v-bind:cuerpo="memo.cuerpo"></Card>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";

export default {
  name: "Memorandums",
  components: {
    Card
  },
  props:{
    data: Array,
  }
};
</script>

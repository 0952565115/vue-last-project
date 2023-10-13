<template>
  <div class="row mt-3">
      <div class="col-md-6">
          <img :src="product.coverimage" alt="" class="img-fluid">
      </div>
          <div class="col-md-6">
              <h1>{{ product.name }}</h1>
              <h4>ราคา {{product.price}} บาท</h4>
          
          </div>
  </div>
  

</template>

<script setup>
import { useRoute } from 'vue-router'
import { ref,computed } from 'vue';

import { useHealthNews_list } from '@/stores/counter.js';

const all_Art = useHealthNews_list();
const list = ref(all_Art.HealthNews_list);

const route = useRoute()

console.log(route.params.id)

const product = computed(() => {
return list.value.find(item => item.id === route.params.id)
})
</script>

<style lang="scss" scoped>

</style>
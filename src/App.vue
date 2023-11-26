<template>
  <div>
    <PriceModal :type="'critical'" />
    <PriceBanner :type="'critical'" />
    <PriceBadge />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import PriceModal from './components/PriceModal.vue'
import PriceBanner from './components/PriceBanner.vue'
import PriceBadge from './components/PriceBadge.vue'

export default defineComponent({
  components: { PriceModal, PriceBanner, PriceBadge }
})
</script>

<style scoped></style>

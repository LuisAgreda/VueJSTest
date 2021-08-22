<template>
  <section>
    <h1 class="font-semibold text-center text-2xl md:text-3xl mt-16 mb-16">
      Lista de favoritos
    </h1>
    <px-states :states="states" :included="included" />
  </section>
</template>

<script>
import json from '../../real_estates.json/real_estates.json'
import PxStates from '@/components/PxStates'

export default {
  name: 'Home',

  components: { PxStates },

  data() {
    return {
      states: json.data,
      included: json.included,
    }
  },
}
</script>

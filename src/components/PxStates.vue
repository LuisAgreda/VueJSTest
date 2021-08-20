<template>
  <section class="mx-6 grid gap-y-16">
    <div v-for="objData in states" :key="objData.id">
      <div class="relative w-full h-48 flex overflow-hidden">
        <div>
          <img
            class="
              h-full
              object-cover
              border-solid border border-black
              rounded-lg
              z-20
            "
            v-for="images in searchingImage(
              objData.attributes.real_estate_ids,
              included,
            )"
            :key="images"
            :src="images"
            :alt="images"
          />
        </div>
        <img
          class="absolute w-full h-full left-0 top-0 z-0"
          src="@/assets/static/images/empty-state.png"
          alt="empty state image"
        />
      </div>
      <span class="mt-5 block text-lg font-semibold">{{
        objData.attributes.name
      }}</span>
      <span class="text-xs font-normal text-gray-700">
        {{ objData.attributes.real_estate_ids.length }} Propiedades guardadas
      </span>
    </div>
    <div class="text-center">
      <div
        class="
          flex
          justify-center
          items-center
          w-full
          h-48
          bg-blue-100
          rounded-xl
        "
      >
        <img
          class="w-12"
          src="@/assets/static/images/plus.svg"
          alt="plus icon"
        />
      </div>
      <span class="block mt-5 text-lg text-blue-700 font-medium"
        >Crear una nueva lista</span
      >
    </div>
  </section>
</template>

<script>
export default {
  name: 'PxStates',

  props: {
    states: {
      type: Array,
      default: () => [],
    },
    included: {
      type: Array,
      default: () => [],
    },
  },

  methods: {
    searchingImage(dataId, includedId) {
      const res = []
      dataId.map(x => res.push(...includedId.filter(y => y.id == x)))
      return res.map(x => x.attributes.gallery_urls[0])
    },
  },
}
</script>

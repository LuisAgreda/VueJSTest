<template>
  <section class="mx-6 grid gap-y-16">
    <div v-for="objData in states" :key="objData.id">
      <div class="relative w-72 h-48">
        <div class="flex rounded-lg h-full cursor-pointer">
          <img
            v-bind:class="{
              'w-36':
                images.id == objData.attributes.real_estate_ids[0] &&
                objData.attributes.real_estate_ids.length > 1,
              'z-30': images.id == objData.attributes.real_estate_ids[0],

              'wd-48':
                images.id == objData.attributes.real_estate_ids[1] &&
                objData.attributes.real_estate_ids.length > 2,
              'z-20': images.id == objData.attributes.real_estate_ids[1],
              'brightness-80':
                images.id == objData.attributes.real_estate_ids[1],

              'z-10': images.id == objData.attributes.real_estate_ids[2],
              'brightness-60':
                images.id == objData.attributes.real_estate_ids[2],
            }"
            class="p-0-2 absolute object-cover rounded-lg h-full"
            v-for="images in searchingImage(
              objData.attributes.real_estate_ids,
              included,
            )"
            :key="images.id"
            :src="images.attributes.gallery_urls[0]"
            :alt="images.attributes.gallery_urls[0]"
          />
        </div>
        <img
          class="absolute w-full h-full left-0 top-0 z-0"
          src="@/assets/static/images/empty-state.png"
          alt="empty state image"
        />
        <span class="absolute t-r-2 z-50 text-lg font-semibold text-white">
          +{{
            objData.attributes.real_estate_ids.length > 3
              ? objData.attributes.real_estate_ids.length - 3
              : 0
          }}
        </span>
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
          object-cover
          cursor-pointer
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
      <span class="cursor-pointer block my-5 text-lg text-blue-700 font-medium">
        Crear una nueva lista
      </span>
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
      return res.map(x => x)
    },
  },
}
</script>

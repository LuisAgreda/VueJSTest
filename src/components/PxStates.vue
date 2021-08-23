<template>
  <section
    class="
      max-w-4xl
      pb-20
      px-6
      lg:m-auto
      grid
      gap-y-14
      md:grid-cols-2
      md:gap-x-8
      lg:grid-cols-3
      overflow-hidden
    "
  >
    <div v-for="objData in states" :key="objData.id">
      <div class="relative w-full h-48 overflow-hidden">
        <div
          @click="handleClick(images.id)"
          v-for="images in searchingImage(
            objData.attributes.real_estate_ids,
            included,
          )"
          :key="images.id"
          class="
            absolute
            w-full
            h-full
            rounded-lg
            border border-white
            duration-500
            hover:w-full
            hover:z-50
          "
          :class="{
            'wd-full': isClick && images.id == idClick,

            'w-3/6':
              objData.attributes.real_estate_ids.length > 1 &&
              images.id == objData.attributes.real_estate_ids[0],
            'z-40': images.id == objData.attributes.real_estate_ids[0],

            'w-3/4':
              objData.attributes.real_estate_ids.length > 2 &&
              images.id == objData.attributes.real_estate_ids[1],
            'z-30': images.id == objData.attributes.real_estate_ids[1],

            'z-20': images.id == objData.attributes.real_estate_ids[2],
          }"
        >
          <div
            class="
              filter
              absolute
              rounded-md
              left-0
              top-0
              h-full
              w-full
              hover:bg-opacity-0 hover:bg-white
            "
            :class="{
              'bg-op-0': isClick && images.id == idClick,
              'bg-lh': images.id == objData.attributes.real_estate_ids[2],
              'bg-gray-400': images.id == objData.attributes.real_estate_ids[1],
              'bg-opacity-25':
                images.id == objData.attributes.real_estate_ids[1],
            }"
          ></div>
          <img
            class="w-full h-full object-cover rounded-md"
            :src="images.attributes.gallery_urls[0]"
            :alt="images.attributes.gallery_urls[0]"
          />
        </div>
        <img
          class="absolute rounded-lg w-full h-full left-0 top-0 z-0"
          src="@/assets/static/images/empty-state.png"
          alt="empty state image"
        />
        <span
          class="
            absolute
            z-50
            text-lg
            font-semibold
            text-white
            top-1/2
            right-10d
            transform
            -translate-y-2/4
          "
        >
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
          class="w-9"
          src="@/assets/static/images/plus.svg"
          alt="plus icon"
        />
      </div>
      <span
        class="cursor-pointer block my-5 text-lg text-blue-700 font-semibold"
      >
        Crear una nueva lista
      </span>
    </div>
  </section>
</template>

<script>
export default {
  name: 'PxStates',

  data() {
    return {
      idClick: [],

      isClick: false,
    }
  },

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
    handleClick(id) {
      this.idClick = this.included.filter(x => x.id == id).map(x => x.id)
      this.isClick = !this.isClick
    },

    searchingImage(dataId, includedId) {
      const res = []
      dataId.map(x => res.push(...includedId.filter(y => y.id == x)))
      return res.map(x => x)
    },
  },
}
</script>

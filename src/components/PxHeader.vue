<template>
  <header class="border-b">
    <nav class="grid grid-cols-2 p-4 lg:px-20 lg:py-0 box-border">
      <div class="flex items-center">
        <img
          class="lg:hidden cursor-pointer w-8 h-8 mr-2"
          src="@/assets/static/images/bars.svg"
          alt="bars icon"
        />
        <img
          class="lg:hidden cursor-pointer w-8 h-8"
          src="@/assets/static/images/la-haus-logo-2.svg"
          alt="La Haus Logo"
        />
        <img
          class="hidden cursor-pointer lg:inline"
          src="@/assets/static/images/la-haus-logo.svg"
          alt="La Haus Logo"
        />
      </div>
      <nav class="flex items-center justify-end">
        <span
          class="
            hover:border-black
            border-b-2 border-white
            cursor-pointer
            hidden
            lg:inline
            text-base
            mr-10
            py-4
          "
          >Cundinamarca</span
        >
        <span
          class="
            hover:border-black
            border-b-2 border-white
            cursor-pointer
            hidden
            lg:inline
            text-base
            mr-10
            py-4
          "
          >Antioquia</span
        >
        <span
          class="
            hover:border-black
            border-b-2 border-white
            cursor-pointer
            hidden
            lg:inline
            text-base
            mr-12
            py-4
          "
          >Recursos</span
        >

        <div class="flex items-center lg:relative">
          <span
            class="
              hover:border-black
              border-b-2 border-white
              cursor-pointer
              hidden
              lg:inline
              text-base
              mr-1
              py-4
            "
            >Mi perfil</span
          >
          <img
            class="hidden lg:inline w-3 cursor-pointer"
            src="@/assets/static/images/angel-down.svg"
            alt="angel drop down icon"
          />
          <img
            class="
              w-3
              absolute
              transform
              -translate-y-4
              translate-x-10
              left-0
              lg:left-auto
              lg:right-0
              lg:translate-x-2
              lg:-translate-y-1
              cursor-pointer
            "
            src="@/assets/static/images/alert-notification.svg"
            alt="point notification icon"
          />
        </div>
      </nav>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'PxHeader',
}
</script>

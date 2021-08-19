<template>
  <header>
    <nav class="grid grid-cols-2">
      <img src="@/assets/static/images/la-haus-logo.svg" alt="La Haus Logo" />
      <nav class="flex">
        <span class="text-base mr-10">Cundinamarca</span>
        <span class="text-base mr-10">Antioquia</span>
        <span class="text-base mr-12">Recursos</span>
        <div class="flex">
          <span class="text-base">Mi perfil</span>
          <img
            class="w-3"
            src="@/assets/static/images/angel-down.svg"
            alt="angel drop down icon"
          />
          <img
            class="w-3"
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

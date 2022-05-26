<script>
export default {
  name: "Component",
  data() {
    return {
      Settings: window.Settings,
      localStorage: localStorage,
    };
  },
  async created() {},
};
</script>
<template>
  <main class="bg-bray-500 p-5">
    <div>
      <h1 class="mt-10 text-5xl text-center font-bold">
        A <span :class="`text-${localStorage.color}`">Gallery</span> for <br />
        my projects.
      </h1>
    </div>
    <div class="w-full grid-cols-3 flex flex-wrap mt-10 grid gap-4">
      <div
        v-for="picture in Settings.gallery.data"
        :key="picture"
        :class="`h-full object-cover ${
          picture.long ? 'col-span-2' : 'col-span-1'
        } `"
      >
        <div :class="`w-full h-full flex flex-wrap`">
          <img :src="picture.image" :class="`rounded w-full object-cover`" />
        </div>
      </div>
    </div>
    <div class="py-3"></div>
  </main>
</template>

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
  <main class="h-screen grid-cols-3 gap-5 p-5 grid">
    <div class="w-full p-5" v-if="Settings.me.avatar">
      <img
        :src="Settings.me.avatar"
        class="duration-300 opacity-60 hover:scale-105 hover:rounded hover:opacity-100 cursor-pointer w-full transition-all bg-bray-400"
      />
    </div>
    <div class="p-5 px-1 col-span-2">
      <div>
        <h1 :class="`font-black py-2 text-6xl`">
          <span>Hi, I'm </span>
          <span :class="`text-${localStorage.color}`">
            {{ Settings.me.firstName }}</span
          >
        </h1>
        <p v-if="Settings.me.about" class="text-2xl">{{ Settings.me.about }}</p>
      </div>
      <div v-if="Settings.navBox" class="mt-4 mr-5">
        <div
          class="gap-5 grid grid-cols-2"
          v-for="box in Settings.navBox.boxes"
          :key="box"
        >
          <a :href="box.url" class="group cursor-pointer">
            <div
              :class="`bg-bray-400 duration-300 transition group-hover:text-white group-hover:bg-${localStorage.color} p-5 rounded group`"
            >
              <h2
                :class="`flex space-x-2`"
                v-html="`${box.icon} <span class=''> ${box.name}</span>`"
              ></h2>
            </div>
          </a>
        </div>
      </div>
    </div>
  </main>
</template>

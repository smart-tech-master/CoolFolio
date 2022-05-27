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
  <main class="bg-bray-500 p-5" v-if="(Settings.me || {}).projects">
    <div>
      <h1 class="mt-10 text-5xl text-center font-bold">
        <span :class="`text-${localStorage.color}`">Projects</span> I've <br />
        contributed to
      </h1>
    </div>
    <div class="w-full grid-cols-3 mt-10 grid gap-4">
      <div v-for="project in Settings.me.projects" :key="project">
        <div
          class="p-4 w-full bg-bray-400 hover:scale-105 rounded duration-300 transition"
        >
          <h1 v-if="project.name" class="text-2xl font-semibold">
            {{ project.name }}
          </h1>
          <p class="text-xs" v-if="project.description">
            {{ project.description }}
          </p>
          <img :src="project.image" class="rounded mt-5 w-full object-cover" />
          <div
            :class="`grid w-full ${
              (project.buttons || []).length == 2
                ? 'grid-cols-2'
                : 'grid-cols-1'
            } gap-3 mt-3`"
          >
            <button
              v-for="button in project.buttons || []"
              :key="button"
              :class="`py-3 text-white rounded text-sm ${
                button.themeColor ? `bg-${localStorage.color}` : 'bg-bray-300'
              }`"
              :href="button.url || ''"
            >
              {{ button.text }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

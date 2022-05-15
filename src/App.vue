<template>
  <div class="relative max-w-xl mx-auto h-screen overflow-hidden border">
    <router-view v-slot="{ Component, route }">
      <transition :name="transitionName">
        <component :is="Component" :key="route.path ? route.path : undefined" />
      </transition>
    </router-view>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { useRouter } from "vue-router";

export default defineComponent({
  setup() {
    const transitionName = ref("slide-left");
    const router = useRouter();

    router.beforeEach((to, from, next) => {
      const toDepth = to.meta.depth as number;
      const fromDepth = from.meta.depth as number;
      transitionName.value = toDepth < fromDepth ? "slide-right" : "slide-left";
      next();
    });

    return { transitionName };
  },
});
</script>

<style>
#app {
  background-color: #efefef;
}

.slide-right-enter-active,
.slide-right-leave-active,
.slide-left-enter-active,
.slide-left-leave-active {
  position: absolute;
  width: 100%;
  will-change: transform;
  transition: all 0.3s ease-out;
}

.slide-right-enter-active {
  transform: translate(-100px, 0);
  z-index: 0;
}
.slide-right-enter-to {
  transform: translate(0, 0);
}
.slide-right-leave-active {
  transform: translate(0%, 0);
  z-index: 1;
}
.slide-right-leave-to {
  transform: translate(100%, 0);
}

.slide-left-enter-active {
  transform: translate(100%, 0);
}
.slide-left-enter-to {
  transform: translate(0, 0);
}

.slide-left-leave-active {
  transform: translate(0%, 0);
}
.slide-left-leave-to {
  transform: translate(-100px, 0);
}
</style>

<script>
export default {
  props: {
    title: {
      type: String,
    },
    author: {
      type: String,
    },
    meeting: {
      type: String,
    },
  }
}
</script>

<template>
  <div v-if="title || social" class="bg-barBottom flex absolute w-full bottom-0 left-0 py-0.5 px-2 text-sm flex-items-center">
    <div class="w-1/3 text-left pl-2 flex">
     {{ author }}
    </div>
    <div class="w-1/3 flex justify-center">
      {{ title }}
    </div>
    <div class="w-1/3 flex justify-end">
      {{ meeting }}
    </div>
    <!-- <div class="w-1/40 p-0 mr-0"> <SlideCurrentNo /> / <SlidesTotal /> </div> -->
  </div>
</template>

<style scoped>

.divider {
  width: 1px; /* Width of the divider line */
  height: 1em; /* Height can be adjusted as needed */
  background-color: azure; /* Color of the divider */
  margin: 2px 10px; /* Spacing around the divider */
}

.bg-barBottom {
  background: #125e0be0;
  background-size: 180% 180%;
  opacity: 1.0;
  animation: gradient-animation 15s ease infinite;
  color:azure;
}

@keyframes gradient-animation {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

</style>
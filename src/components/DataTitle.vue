<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10 italic text-gray-500">
      updated {{ timestamp }}
    </div>
  </div>
</template>

<script>
import dayjs from 'dayjs';
import relativeTime from 'dayjs/plugin/relativeTime';


import { computed } from 'vue';
export default {
  name: 'DataTitle',
  props: ['text', 'dataDate'],
  created(){
    dayjs.extend(relativeTime);
  },
  setup ({ dataDate }) {
    return {
      timestamp: computed(() => dayjs(dataDate).fromNow())
    };
  }
};
</script>
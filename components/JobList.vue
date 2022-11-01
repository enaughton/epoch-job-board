<script>
import { EditIcon, Trash2Icon } from 'vue-feather-icons'

export default {
  components: {
    EditIcon,
    Trash2Icon,
  },
  props: {
    job: {
      type: Object,
      default: () => ({}),
    },
  },

}
</script>


<template>
  <li
    class="
      p-4
      mb-3
      flex
      bg-white
      shadow
      rounded-lg
      cursor-move
    "
  >


    <div

      class="p-4 bg-white sm:rounded-lg hover:bg-green-200"
    >
      <div class="flex flex-row gap-8 p-4">
        <h2 class="text-2xl font-semibold leading-7">{{ job.title }}</h2>
      </div>
      <p>{{ job.description }}</p>
      <ul class="p-4">
        <li v-for="item in job.benefits" :key="item" class="list-disc">
          {{ item }}
        </li>
      </ul>

      <a
        v-if="job.email"
        class="p-2 overflow-hidden bg-white border-2 border-green-500 rounded  hover:bg-green-500"
        :href="'mailto:' + job.email + '?subject=' + job.title"
        target="_black"
      >
        Email Us
      </a>
    </div>
  </div>


  </li>
</template>

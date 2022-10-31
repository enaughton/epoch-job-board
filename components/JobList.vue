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

  methods: {
    onEdit(job) {
      alert(`editing ${job.title}`)
    },
    onDelete(job) {
      alert(`Deleting ${job.title}`)
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
      justify-between
      items-center
      bg-white
      shadow
      rounded-lg
      cursor-move
    "
  >
    <div class="flex items-center">
      <p class="ml-2 text-gray-700 font-semibold font-sans tracking-wide">
        {{ job.title }}
      </p>
    </div>
    <div class="flex">
      <button
        aria-label="Edit user"
        class="
          p-1
          focus:outline-none focus:shadow-outline
          text-teal-500
          hover:text-teal-600
        "
        @click="onEdit(job)"
      >
        <EditIcon />
      </button>
      <button
        aria-label="Delete user"
        class="p-1 focus:outline-none focus:shadow-outline hover:text-red-600"
        @click="onDelete(job)"
      >
        <Trash2Icon />
      </button>
    </div>
  </li>
</template>

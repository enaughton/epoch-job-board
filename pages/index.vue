<template>
  <div class="bg-gradient-to-br from-green-600">
    <Header />
    <div
      id="app"
      class="
        min-h-screen
        w-screen
        flex flex-col
        pt-20
        justify-center
        items-center
        md:items-start md:flex-row
      "
    >
      <div class="w-full max-w-md bg-green text-center px-3">
        <p class="mb-2 text-gray-700 font-semibold font-sans tracking-wide">
          Active Jobs
        </p>

        <Draggable
          tag="ul"
          class="w-full max-w-md"
          ghost-class="moving-card"
          group="all-jobs"
          :list="users"
          :animation="200"
        >
          <JobList
            v-for="job in jobs"
            :job="job"
            :key="job.title"
            @on-edit="onEdit"
            @on-delete="onDelete"
          >
          </JobList>
        </Draggable>
      </div>
      <div class="w-full max-w-md ml-12 text-center">
        <p class="mb-2 text-gray-700 font-semibold font-sans tracking-wide">
          Completed Applications
        </p>
        <Draggable
          tag="ul"
          ghost-class="moving-card"
          group="all-jobs"
          :list="appliedJobs"
          :animation="200"
        >
          <JobList
            v-for="job in appliedJobs"
            :job="job"
            :key="job.title"
            @on-edit="onEdit"
            @on-delete="onDelete"
          >
          </JobList>
        </Draggable>
      </div>
    </div>
  </div>
</template>

<script>
import Draggable from 'vuedraggable'
import jobs from '/jobs.json'
export default {
  components: {
    Draggable,
  },
  data() {
    return {
      jobs: jobs
    }
  },
  name: 'IndexPage',
}
</script>
s

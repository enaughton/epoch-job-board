<template>
  <div class="bg-gradient-to-br from-green-600">
    <Header />
    <div
      id="app"
      class="
        min-h-screen
        w-screen
        pt-20
        grid
        md:items-start md:flex-row lg:grid-cols-2

      "
    >
   <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
      <p class="mb-2 text-black font-semibold text-center font-sans tracking-wide">
        Active Jobs
      </p>

      <Board>
        <Draggable
          tag="ul"
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
      </Board>
      </div>
      <div class="">
        <p class="mb-2 text-black font-semibold font-sans text-center tracking-wide">
          Completed Applications
        </p>
        <Board>
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

         />

        </Draggable>
        </Board>
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
  }
}
</script>


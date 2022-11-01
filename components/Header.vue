<script>

export default {
methods: {
  openSettings(){
    alert('View all Adventures')
  }
}
}
</script>

<template>

    <header class="shrink-0 flex justify-between bg-white px-4 py-3">
      <a class="text-2xl font-black tracking-tight" href="/">Adventurers Wanted</a>
      <nav>
        <button class="text-sm font-medium px-3 py-2 rounded-md hover:bg-gray-100" @click="openSettings">My Adventures</button>
        <button class="ml-3">
          <img class="h-9 w-9 inline rounded-full" src="	https://pbs.twimg.com/profile_images/1296425733020176385/tcO9mjan_400x400.jpg" alt="">
        </button>
      </nav>
    </header>

</template>

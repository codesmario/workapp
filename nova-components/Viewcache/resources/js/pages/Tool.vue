<template>
  <div>
    <Head title="Viewcache" />

    <Heading class="mb-6">View Cache</Heading>

    <Card
      class="flex flex-col items-center justify-center"
      style="min-height: 300px"
    >

      <h1 class="dark:text-white text-4xl font-light mb-6">
        Enable your Application View Cache.
      </h1>

      <button @click="activateCache" class="flex-shrink-0 shadow rounded focus:outline-none ring-primary-200 dark:ring-gray-600 focus:ring bg-primary-500 hover:bg-primary-400 active:bg-primary-600 text-white dark:text-gray-800 inline-flex items-center font-bold px-4 h-9 text-sm flex-shrink-0">Enable Cache</button>

    </Card>
  </div>
</template>

<script>
export default {
  mounted() {
    //
  },
  methods: {
    activateCache() {
      Nova.request().post('/nova-vendor/viewcache').then(data => {
        alert('success');
      })
    }
  }
}
</script>

<style>
/* Scoped Styles */
</style>

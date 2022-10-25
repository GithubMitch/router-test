<template>
  <div>
    <ul>
      <li>
        1. Navigate in this order > topups > giftcards > topups > home > topup > home
      </li>
    </ul>

    <NuxtPage v-if="nuxtPage" />
    <router-view v-else />

    <p>Now rendering page with <button @click="nuxtPage ? nuxtPage = false : nuxtPage = true;">{{nuxtPage == true ? '<NuxtPage/>' : '<router-view>'}}</button></p>


  </div>
</template>

<script>

export default defineComponent({
  async setup() {
    const nuxtPage = ref(false)
    return {nuxtPage}
  }
})
</script>
<template>
  <div>
    <ul>
      <li>1. Navigate in this order > topups > giftcards > topups > home > topup > home & Check invalid route params</li>
      <li>2. Navigate to Home , hit a hard Refresh (cmd | ctrl + shift + r)</li>
      <li>3. Press toggle bottom at bottom of page to now render these dynamic pages with NuxtPage component</li>
      <li>4. Navigate in this order > topups > giftcards > topups > home > topup > home & Check VALID route params</li>
      <li>5. What is the appropriate usage, and functionality for router-view component,also what is the difference in using nuxtpage here ? 
            And why can i only find unofficial implementations instead of official docs ? </li>
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
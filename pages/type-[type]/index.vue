<template>
  <main>
    <nav>
      <NuxtLink :to="`/`"> Home</NuxtLink>
      <NuxtLink :to="`/type-topups/`">Topups</NuxtLink> 
      <NuxtLink :to="`/type-giftcards/`">Giftcards</NuxtLink>   
    </nav>
    <h1>Type</h1>
    <div id="params">
      Rendered by {{nuxtPage ? "nuxtPage" : "router-view"}}
      <p :class="{expected: $route.params.type === route.params.type}"><strong>route.params:  </strong> {{route.params.type}}</p>
      <p class="expected"><strong>$route.params: </strong> {{$route.params.type}}</p>
    </div>
  </main>
</template>

<script>
export default defineComponent({
props: {
  nuxtPage: {
    type: Boolean,
    default: false
  }
},
setup() {
  const route = useRoute();
  onMounted(() => {console.log(route.params)})
  return {route}
}})
</script>
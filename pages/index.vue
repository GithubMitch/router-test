<template>
  <main>
    <nav>
      <NuxtLink :to="`/`"> Home</NuxtLink>
      <NuxtLink :to="`/type-topups/`">Topups</NuxtLink> 
      <NuxtLink :to="`/type-giftcards/`">Giftcards</NuxtLink>   
    </nav>
    <h1>Home</h1>
    <div id="params">
      <p :class="{expected: $route.params.type === route.params.type}"><strong>route.params:  </strong> {{route.params.type}}</p>
      <p class="expected"><strong>$route.params: </strong> {{$route.params.type}}</p>
    </div>
  </main>
</template>

<script>

export default defineComponent({
  async setup() {
    const route = useRoute();

    const expected = computed( () => {
      return route.params.type === 'beltegoed';
    })

    return {route}
  }
})
</script>

<style>
  nav a {
    color:black;
    font-size:18px;
    padding: 0 1em;
  }
  #params p {
    font-size:20px;
    color:red;
  }
  #params p.expected {
    color:green;
  }

</style>
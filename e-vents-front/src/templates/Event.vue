<template>
  <Layout>
    <h1>{{ $page.event.title }}</h1>
    <img :src="`http://localhost:1337${$page.event.image}`" :alt="$page.event.title">
    <p>{{ $page.event.description }}</p>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
	event(id: $id) {
    id,
    title,
    description,
    price,
    duration,
    date,
    image
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.event.title
    }
  }
}
</script>
<template>
  <Layout>
    <div>
    	<h1 v-html="$page.product.title" />
    	<div v-html="$page.product.price" />
      <ul>
        <li v-for="image in $page.product.images">
          <g-image :src="image"/>
        </li>
      </ul>
    </div>
  </Layout>
</template>

<script>
  export default {
    metaInfo() {
      return {
        title: this.$page.product.title
      }
    }
  }
</script>

<page-query>
query ($id: ID!) {
  product(id: $id) {
    title
    price
    images
  }
}
</page-query>

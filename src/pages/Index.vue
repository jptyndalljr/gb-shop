<template>
  <Layout>
    <section class="hero">
      <div class="container">
        <h1>Welcome to GB Shop</h1>
        <!-- <ConsoleCard name="Gameboy Color" image="gbc_clean.png"/> -->
      </div>
    </section>
    <section class="main">
      <p>Posts</p>
      <div v-for="edge in $page.posts.edges" :key="edge.node.id">
        <h2>{{ edge.node.title }}</h2>
        <p>{{ edge.node.date }}</p>
        <g-link :to="edge.node.path">Read more</g-link>
      </div>
      <p>Products</p>
      <div v-for="edge in $page.product.edges" :key="edge.node.id">
        <h2>{{ edge.node.title }}</h2>
        <p>{{ edge.node.price }}</p>
        <g-link :to="edge.node.path">Read more</g-link>
      </div>
    </section>
  </Layout>
</template>

<style lang="scss">
  .hero {
    h1 {
      text-align: center;
    }
  }
</style>

<script>
import ConsoleCard from '~/components/ConsoleCard.vue'

export default {
  components: {
    ConsoleCard
  },
  metaInfo: {
    title: 'Home'
  }
}
</script>

<page-query>
  query {
    posts: allPost {
      edges {
        node {
          id
          title
          date(format: "MMMM DD, YYYY")
          path
        }
      }
    }
    product: allProduct {
      edges {
        node {
          id
          title
          price
          description
          images
          path
        }
      }
    }
  }
</page-query>

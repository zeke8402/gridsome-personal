<template>
  <Layout>
    <h1>Blog</h1>
    
    <ul>
      <li v-for="edge in $page.pages.edges" :key="edge.node.path">
        <g-link :to="edge.node.path">{{ edge.node.path }}</g-link>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
query Pages {
  pages: allBlogPost {
    edges {
      node {
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Blog',
  }
}
</script>

<template>
  <Layout>
    <h1 class="text-xl font-semibold mb-2 text-betathree">{{ $page.post.title }}</h1>
    <span class="font-light">{{ $page.post.date }}</span>
    <div class="mt-4" v-html="$page.post.content" />
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  post: blogPost (path: $path) {
    title
    date (format: "MMMM D, Y")
    content
  }
}
</page-query>

<script>
export default {
  metaInfo () {
    return {
      title: this.$page.post.title
    }
  },
}
</script>
<style>
.markdown {
  @apply text-lg text-grey-darkest leading-normal;
  & > * + *,  & li + li, & li > p + p {
    @apply mt-6;
  }
  & strong {
    @apply text-black font-bold;
  }
  & a {
    @apply text-black font-semibold;
  }
  & strong a {
    @apply font-bold;
  }
  & h2 {
    @apply leading-tight text-xl font-bold text-black mb-2 mt-10;
  }
  & h3 {
    @apply leading-tight text-lg font-bold text-black mt-8 -mb-2;
  }
  & code {
    @apply font-mono text-sm inline bg-grey-lighter px-1;
  }
  & pre code {
    @apply block bg-black p-4 rounded;
  }
  & blockquote {
    @apply border-l-4 border-grey-light pl-4 italic;
  }
  & ul, & ol {
    @apply pl-5;
    @screen sm {
      @apply pl-10;
    }
  }
}
</script>

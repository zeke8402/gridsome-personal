<template>
  <div class="min-h-screen flex flex-col bg-betaone text-betafour">
    <div class="container max-w-screen-md mx-auto px-5">
      <header class="flex justify-between items-center mt-8 mb-12 text-betafour">
        <strong>
          <g-link to="/">{{ $static.metadata.siteName }}</g-link>
        </strong>
        <nav>
          <g-link to="/">Home</g-link>
          <g-link class="ml-6 text-betathree" to="/about/">About</g-link>
          <g-link class="ml-6 text-betathree" to="/blog/">Blog</g-link>
          <g-link class="ml-6 text-betathree" to="/three/">Threejs</g-link>
        </nav>
      </header>
      <transition name="fade" appear>
      <main>
        <slot/>
      </main>
      </transition>
    </div>
  </div>
</template>

<static-query>
  query {
  metadata {
  siteName
  }
  }
</static-query>
<style>

.fade-enter-active {
  transition: opacity .5s;
}

.fade-enter {
  opacity: 0;
}
</style>

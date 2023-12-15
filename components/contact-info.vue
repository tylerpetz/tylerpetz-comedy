<script>
export default {
  name: 'contact-info',
  data() {
    return {
      phrases: ['I love connections', 'I\'m so lonely', 'I won\'t spam you', 'Or just leave']
    }
  }
}
</script>

<template>
  <section class="max-w-xl rounded bg-theme-bg-d text-center mx-auto mb-16 px-6 py-10">
    <h1 class="text-theme-text-l text-lg md:text-2xl mb-6">
      <slot name="header">
        Connect with me
      </slot>
    </h1>
    <p class="text-theme-text-l md:text-lg mb-8">
      <slot name="body">
        {{ phrases[Math.floor(Math.random() * phrases.length)] }}
      </slot>
    </p>
    <ul class="flex items-center justify-center space-x-8">
      <li>
        <a
          aria-label="Tyler's Instagram"
          target="_blank"
          href="https://www.instagram.com/tyler.petz"
        >
          <svg-icon
            class="h-6 w-6 text-theme-link hover:text-theme-link-hover transition-colors duration-75 flex-shrink-0"
            name="instagram"
          />
        </a>
      </li>
    </ul>
  </section>
</template>

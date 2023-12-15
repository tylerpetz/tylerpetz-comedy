<script>
export default {
  name: 'the-shoes',
  data() {
    return {
      links: [
        {
          name: 'Instagram',
          url: 'https://www.instagram.com/tyler.petz',
          icon: 'fab fa-instagram'
        },
        // {
        //   name: 'Linkedin',
        //   url: 'https://www.linkedin.com/in/tyler-petz-11734818/',
        //   icon: 'fab fa-linkedin'
        // }
      ]
    }
  }
}
</script>

<template>
  <footer class="h-20 px-4 md:px-8 bg-mod-cap text-mod-legend flex items-center print:hidden">
    <div class="w-full max-w-screen-lg mx-auto flex justify-between items-center">
      <p class="text-sm sm:text-base md:text-lg">
        Tyler Petz &copy; {{ new Date().getFullYear() }}
      </p>
      <ul class="flex flex-row space-x-4 text-lg md:text-2xl">
        <li
          v-for="link in links"
          :key="link.name"
        >
          <a
            class="text-mod-legend hover:text-theme-link transition-colors duration-75"
            :href="link.url"
            target="_blank"
            rel="noopener noreferrer"
            :aria-label="`Tyler's ${link.name}`"
          >
            <svg-icon
              class="h-6 w-6 text-theme-link hover:text-theme-link-hover transition-colors duration-75 flex-shrink-0"
              name="instagram"
            />
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

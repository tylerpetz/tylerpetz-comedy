<script>
import createClient from '@/app/contentful'

export default {
  name: 'home',
  asyncData({ $config }) {
    const client = createClient($config.spaceId, $config.accessToken)
    return Promise.all([
      client.getEntries({
        content_type: 'standupCredit',
        order: '-sys.createdAt'
      }),
      client.getEntries({
        content_type: 'standupShow',
        order: '-sys.createdAt'
      }),
      client.getEntries({
        content_type: 'standupVideo',
        order: 'sys.createdAt'
      })
    ]).then(([credits,shows,videos]) => {
      return {
        credits: credits.items,
        shows: shows.items,
        videos: videos.items,
      }
    })
  },
  data() {
    return {
      credits: [],
      shows: [],
      videos: [],
    }
  },
}
</script>

<template>
  <div>
    <div class="flex flex-col items-center pb-32">
      <h1 class="text-center text-xl sm:text-2xl md:text-4xl">
        Tyler Petz
      </h1>
      <h2 class="text-center rounded-sm text-lg sm:text-2xl md:text-3xl mt-4 mb-6 bg-accent-cap text-accent-legend pt-1 px-3">
        stand-up comedian
      </h2>
    </div>
    <base-divider />
    <contact-info />
  </div>
</template>

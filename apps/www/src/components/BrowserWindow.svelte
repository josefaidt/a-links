<script lang="ts">
  import { onMount } from 'svelte'

  const alinks = [
    {
      keyword: 'a/github',
      url: 'https://github.com/josefaidt/a-links',
      image: '/screenshots/github.png',
    },
    {
      keyword: 'a/twitter',
      url: 'https://twitter.com/josefaidt',
      image: '/screenshots/twitter.png',
    },
    {
      keyword: 'a/help/1',
      url: 'https://github.com/josefaidt/a-links/issues/1',
      image: '/screenshots/help.png',
    },
    {
      keyword: 'a/links',
      url: 'https://a-links.io',
    },
  ]

  let lastUrl: string | null = null
  let url: string | null = null

  $: i = 0
  $: alink = alinks[i]
  // store the last url in order to always show an image in the "browser"
  $: lastUrl = null
  $: url = null

  // url should type keyword
  const createUrlCycle = () => {
    const length = alink.keyword.length
    let count = 0
    return () => {
      if (count < length) {
        count++
        url = alink.keyword.slice(0, count + 1)
        return url
      } else if (count < length * 2) {
        // ... wait a second or two
        count++
        return url
      } else if (count < length * 4) {
        // resolve the final url
        count++
        lastUrl = alink.url
        return alink.url
      } else {
        // move on to the next url
        count = 0
        i = (i + 1) % alinks.length
        // return '|'
        return null
      }
    }
  }

  onMount(() => {
    const urlCycle = createUrlCycle()

    const urlInnterTimer = setInterval(() => {
      url = urlCycle()
    }, 150)

    return () => {
      clearInterval(urlInnterTimer)
    }
  })
</script>

<div
  class="border border-gray-200 shadow-2xl rounded-tl-lg rounded-tr-lg bg-gray-100 px-4 sm:px-0"
>
  <div
    class="py-2 px-4 bg-gray-200 rounded-tl-md rounded-tr-md flex items-center"
  >
    <div class="rounded-full h-4 w-4 bg-red-400 flex mr-2"></div>
    <div class="rounded-full h-4 w-4 bg-yellow-400 flex mr-2"></div>
    <div class="rounded-full h-4 w-4 bg-green-400 flex mr-2"></div>
    <div
      class="flex-auto px-2 py-1 ml-3 mr-1 rounded-md bg-white text-s whitespace-nowrap overflow-x-hidden"
    >
      {#if url}
        {url}
      {:else}
        &nbsp;
      {/if}
    </div>
  </div>
  <div class="bg-white max-h-80 overflow-hidden h-80">
    {#each alinks as alink}
      <div class:hidden="{lastUrl !== alink.url}">
        {#if alink.url.includes('a-links.io')}
          <iframe
            class="w-full h-80"
            src="{alink.url}"
            frameborder="0"
            title="{alink.keyword}"
            scrolling="no"
          >
          </iframe>
        {:else}
          <img src="{alink.image}" alt="{alink.keyword}" />
        {/if}
      </div>
    {/each}
  </div>
  <slot />
</div>

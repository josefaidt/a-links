<script>
  import Logo from './Logo.svelte'
  import { MARKETPLACE_URL } from '../lib/constants'
  export let isNavOpen = false
</script>

<div class="px-6 pt-6 lg:px-8">
  <div>
    <nav class="flex h-9 items-center justify-between" aria-label="Global">
      <div class="flex lg:min-w-0 lg:flex-1" aria-label="Global">
        <Logo />
      </div>
      <div class="flex lg:hidden">
        <button
          type="button"
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
          on:click="{() => (isNavOpen = true)}"
        >
          <span class="sr-only">Open main menu</span>
          <!-- Heroicon name: outline/bars-3 -->
          <svg
            class="h-6 w-6"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"></path>
          </svg>
        </button>
      </div>
      <!-- <div
        class="hidden lg:flex lg:min-w-0 lg:flex-1 lg:justify-center lg:gap-x-12"
      >
        <a
          href="#product"
          class="font-semibold text-gray-900 hover:text-gray-900">Product</a
        >

        <a
          href="#features"
          class="font-semibold text-gray-900 hover:text-gray-900">Features</a
        >
      </div> -->
      <div class="hidden lg:flex lg:min-w-0 lg:flex-1 lg:justify-end">
        <a
          href="{MARKETPLACE_URL}"
          class="inline-block rounded-lg px-3 py-1.5 text-sm font-semibold leading-6 text-gray-900 shadow-sm ring-1 ring-gray-900/10 hover:ring-gray-900/20"
        >
          Add to Chrome
        </a>
      </div>
    </nav>
    <!-- Mobile menu, show/hide based on menu open state. -->
    {#if isNavOpen}
      <div role="dialog" aria-modal="true">
        <div
          focus="true"
          class="fixed inset-0 z-10 overflow-y-auto bg-white px-6 py-6 lg:hidden"
        >
          <div class="flex h-9 items-center justify-between">
            <div class="flex">
              <Logo />
            </div>
            <div class="flex">
              <button
                type="button"
                class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
                on:click="{() => (isNavOpen = false)}"
              >
                <span class="sr-only">Close menu</span>
                <!-- Heroicon name: outline/x-mark -->
                <svg
                  class="h-6 w-6"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M6 18L18 6M6 6l12 12"></path>
                </svg>
              </button>
            </div>
          </div>
          <div class="mt-6 flow-root">
            <div class="-my-6 divide-y divide-gray-500/10">
              <!-- <div class="space-y-2 py-6">
                <a
                  href="#product"
                  class="-mx-3 block rounded-lg py-2 px-3 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-400/10"
                  >Product</a
                >

                <a
                  href="#features"
                  class="-mx-3 block rounded-lg py-2 px-3 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-400/10"
                  >Features</a
                >
              </div> -->
              <div class="py-6">
                <a
                  href="{MARKETPLACE_URL}"
                  class="-mx-3 flex rounded-lg py-2.5 px-3 text-base font-semibold leading-6 text-gray-900 hover:bg-gray-400/10"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Add to Chrome
                  <!-- <span class="inline ml-1.5"
                    ><svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      class="w-4 h-4"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25"
                      ></path>
                    </svg></span
                  > -->
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    {/if}
  </div>
</div>

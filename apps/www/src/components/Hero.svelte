<script>
  import { MARKETPLACE_URL, GITHUB_URL, branding } from '../lib/constants'
</script>

<div class="relative px-6 lg:px-8">
  <div class="mx-auto max-w-4xl pt-32 pb-24 sm:pt-40 sm:pb-32">
    <div>
      <div class="hidden sm:mb-8 sm:flex sm:justify-center">
        <div
          class="relative overflow-hidden rounded-full py-1.5 px-4 text-sm leading-6 ring-1 ring-gray-900/10 hover:ring-gray-900/20"
        >
          <span class="text-gray-600">
            Join the party 🎉
            <!-- <a href="#" class="font-semibold text-rose-600">
              <span class="absolute inset-0" aria-hidden="true"></span>Read
              more
              <span aria-hidden="true">&rarr;</span></a
            > -->
          </span>
        </div>
      </div>
      <div>
        <h1
          class="text-4xl font-bold tracking-tight sm:text-center sm:text-6xl"
        >
          {branding.tagline}
        </h1>
        <!-- <p class="mt-6 text-lg leading-8 text-gray-600 sm:text-center">
          Anim aute id magna aliqua ad ad non deserunt sunt. Qui irure qui lorem cupidatat
          commodo. Elit sunt amet fugiat veniam occaecat fugiat aliqua.
        </p> -->
        <div class="mt-8 flex gap-x-4 sm:justify-center">
          <a
            href="{MARKETPLACE_URL}"
            class="inline-block rounded-lg bg-rose-600 px-4 py-1.5 text-base font-semibold leading-7 text-white shadow-sm ring-1 ring-rose-600 hover:bg-rose-700 hover:ring-rose-700"
          >
            Add to Chrome
            <span class="text-rose-200" aria-hidden="true">&rarr;</span>
          </a>
          <a
            href="{GITHUB_URL}"
            class="inline-block rounded-lg px-4 py-1.5 text-base font-semibold leading-7 text-gray-900 ring-1 ring-gray-900/10 hover:ring-gray-900/20"
          >
            GitHub
            <span class="text-gray-400" aria-hidden="true">&rarr;</span>
          </a>
        </div>
      </div>
    </div>
  </div>
</div>

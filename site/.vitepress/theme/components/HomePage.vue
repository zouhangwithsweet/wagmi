<script setup lang="ts">
import type DefaultTheme from 'vitepress/theme'
import { VPButton, VPSponsors, VPTeamMembers } from 'vitepress/theme'
import { useSponsors } from '../composables/useSponsors'

const { data: sponsors } = useSponsors()

const teamMembers = [
  {
    avatar: 'https://www.github.com/tmm.png',
    name: 'awkweb',
    links: [
      { icon: 'github', link: 'https://github.com/tmm' },
      { icon: 'twitter', link: 'https://twitter.com/awkweb' },
    ],
  },
  {
    avatar: 'https://www.github.com/jxom.png',
    name: 'jxom',
    links: [
      { icon: 'github', link: 'https://github.com/jxom' },
      { icon: 'twitter', link: 'https://twitter.com/_jxom' },
    ],
  },
] satisfies DefaultTheme.TeamMember[]
</script>

<template>
  <div class="content">
    <div class="content-container">
      <main class="main">
        <div class="vp-doc" flex flex-col items-center mt-10>
          <h2 id="meet-the-team" op50 font-normal p="t-10 b-2">
            Meet The Team
          </h2>
          <div w-full p-10>
            <VPTeamMembers size="small" :members="teamMembers" />
          </div>

          <h2 id="sponsored-by" op50 font-normal pt-5 pb-2>
            Sponsored by
          </h2>

          <div w-full p-10 class="container">
            <VPSponsors v-if="sponsors" :data="sponsors" />

            <div pt-10 text-center>
              <VPButton theme="sponsor" text="Become a sponsor" href="https://github.com/sponsors/wevm" />
            </div>
          </div>

          <p text-gray text-center opacity-75 pt-10>
            <a class='VercelBadge' target='_blank' rel='noopener noreferrer' title='vercel.com homepage'
              href='https://vercel.com?utm_source=wagmi.sh'>
              <span>Powered by</span>
              <svg height="20" viewBox='0 0 283 64' fill='none'>
                <title>Vercel</title>
                <path fill='currentColor'
                  d='M141.04 16c-11.04 0-19 7.2-19 18s8.96 18 20 18c6.67 0 12.55-2.64 16.19-7.09l-7.65-4.42c-2.02 2.21-5.09 3.5-8.54 3.5-4.79 0-8.86-2.5-10.37-6.5h28.02c.22-1.12.35-2.28.35-3.5 0-10.79-7.96-17.99-19-17.99zm-9.46 14.5c1.25-3.99 4.67-6.5 9.45-6.5 4.79 0 8.21 2.51 9.45 6.5h-18.9zM248.72 16c-11.04 0-19 7.2-19 18s8.96 18 20 18c6.67 0 12.55-2.64 16.19-7.09l-7.65-4.42c-2.02 2.21-5.09 3.5-8.54 3.5-4.79 0-8.86-2.5-10.37-6.5h28.02c.22-1.12.35-2.28.35-3.5 0-10.79-7.96-17.99-19-17.99zm-9.45 14.5c1.25-3.99 4.67-6.5 9.45-6.5 4.79 0 8.21 2.51 9.45 6.5h-18.9zM200.24 34c0 6 3.92 10 10 10 4.12 0 7.21-1.87 8.8-4.92l7.68 4.43c-3.18 5.3-9.14 8.49-16.48 8.49-11.05 0-19-7.2-19-18s7.96-18 19-18c7.34 0 13.29 3.19 16.48 8.49l-7.68 4.43c-1.59-3.05-4.68-4.92-8.8-4.92-6.07 0-10 4-10 10zm82.48-29v46h-9V5h9zM36.95 0L73.9 64H0L36.95 0zm92.38 5l-27.71 48L73.91 5H84.3l17.32 30 17.32-30h10.39zm58.91 12v9.69c-1-.29-2.06-.49-3.2-.49-5.81 0-10 4-10 10V51h-9V17h9v9.2c0-5.08 5.91-9.2 13.2-9.2z' />
              </svg>
            </a>
          </p>
        </div>
      </main>
    </div>
  </div>
</template>

<style>
.vp-doc .VPTeamMembers.small.count-2 .container {
  max-width: calc(276px * 2 + 24px) !important;
}

.container {
  margin: 0 auto;
  max-width: 1152px;
}

h3.vp-sponsor-tier {
  margin: 0;
  margin-bottom: 4px;
}

.VercelBadge {
  align-items: center;
  color: var(--vp-c-text-2) !important;
  display: flex;
  font-size: 0.85rem;
  font-weight: 500;
  gap: 0.35rem;
  justify-content: center;
}

.VercelBadge:hover {
  text-decoration: none !important;
}

.VercelBadge svg {
  color: var(--vp-c-text-2);
  height: 0.85rem;
}
</style>


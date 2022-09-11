<script lang="ts" setup>
export interface IMenuItem {
  type: 'link' | 'button'
  text: string
  href?: any
  route?: any
}

const { t } = useLang()
const menus = computed((): IMenuItem[] => [
  { type: 'link', text: t('for_you.nav'), route: { name: 'index' } },
  { type: 'link', text: t('follow.nav'), route: { name: 'follow' } },
])
</script>

<template>
  <BuilderNavbar>
    <template #search>
      <div
        p="x-3 t-3"
        display="flex"
        align="items-center"
        justify="between"
        bg="white"
        class="search"
        box="border"
      >
        <div
          w="1.6rem"
          h="1.6rem"
          m="r-1"
          bg="logo-banner contain"
          class="bg-logo-banner"
        ></div>
        <div
          display="flex"
          align="items-center"
          justify="center"
          bg="gray-100"
          border="none rounded-2xl"
          flex="1"
          h="33px"
          position="relative"
          text="gray-300"
          class="search-input"
        >
          <img
            w="1.05rem"
            h="1.05rem"
            src="https://static3w.kuaikanmanhua.com/_nuxt/static-kkfront-mobile/image/search_icon.8cb94f3.png"
            class="icon"
          />
          <span>搜索作品名</span>
        </div>
        <div m="mr-1" display="flex" align="items-center" class="booklist">
          <img
            w="1.05rem"
            h="1.05rem"
            src="https://static3w.kuaikanmanhua.com/_nuxt/static-kkfront-mobile/image/booklist_icon.40fddad.png"
            class="icon"
          />
          <span>书架</span>
        </div>
      </div>
    </template>
    <template #menu>
      <div
        w="full"
        align="items-center"
        justify="center"
        display="flex"
        po="relative"
        m="l-auto"
      >
        <nav
          class="text-sm leading-6 font-semibold text-gray-600 dark:text-gray-300"
          role="navigation"
        >
          <ul class="flex items-center space-x-8">
            <li v-for="(item, i) in menus" :key="i">
              <Anchor
                v-if="item.type === 'link'"
                :to="item.route ? item.route : undefined"
                :href="item.href ? item.href : undefined"
                class="hover:no-underline hover:text-slate-900 hover:dark:text-white capitalize"
              >
                {{ item.text }}
                <p></p>
              </Anchor>
            </li>
          </ul>
        </nav>
      </div>
    </template>
  </BuilderNavbar>
</template>

<script setup lang="ts">
import TelegramIcon from '~/assets/icons/telegram.svg'

interface FooterInfoItem {
  title: string
  content: string[]
  link?: string
}

interface FooterSocialLink {
  name: string
  url: string
}

const footerInfoItems: FooterInfoItem[] = [
  {
    title: 'For all questions',
    content: ['+7 (920) 278—00—68', 'qtim@agency.com'],
  },
  {
    title: 'Office in Russia',
    content: ['139 Ruben Station Lake Drew, NM 52678'],
    link: 'https://t.me/sad_arty',
  },
  {
    title: 'Office in Dubai',
    content: ['139 Ruben Station Lake Drew, NM 52678'],
    link: 'https://t.me/sad_arty',
  },
]

const footerSocialLinks: FooterSocialLink[] = [
  {
    name: 'Facebook',
    url: 'https://www.facebook.com',
  },
  {
    name: 'Instagram',
    url: 'https://www.instagram.com',
  },
  {
    name: 'Telegram',
    url: 'https://telegram.org/',
  },
  {
    name: 'Behance',
    url: 'https://www.behance.com',
  },
  {
    name: 'Linkedn',
    url: 'https://www.linkedin.com',
  },
  {
    name: 'Privacy Policy',
    url: 'https://qtim.pro/',
  },
]
</script>

<template>
  <footer id="footer">
    <section class="footer-content">
      <div class="footer-content__top">
        <div class="footer-content__top-left">
          <div class="footer-content__top-left__sub">
            Is there a project?
          </div>

          <div class="footer-content__top-left__cap">
            Let’s work together
          </div>
        </div>
        <div class="footer-content__top-right">
          <div v-for="item in footerInfoItems" :key="item.title" class="footer-content__top-right__item">
            <div class="footer-content__top-right__item-title">
              {{ item.title }}
            </div>

            <div v-for="content in item.content" :key="content" class="footer-content__top-right__item-content">
              {{ content }}
            </div>

            <div v-if="item.link" class="footer-content__top-right__item-link">
              <a :href="item.link" target="_blank">
                <TelegramIcon />
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="footer-content__bottom">
        <ul class="footer-content__bottom-links">
          <li v-for="socialLink in footerSocialLinks.slice(0, 3)" :key="socialLink.name" class="footer-content__bottom-links__item">
            <a :href="socialLink.url" target="_blank">
              {{ socialLink.name }}
            </a>
          </li>
        </ul>

        <div class="footer-content__bottom-btn">
          <span class="footer-content__bottom-btn__text">
            GO
          </span>
        </div>

        <ul class="footer-content__bottom-links">
          <li v-for="socialLink in footerSocialLinks.slice(3)" :key="socialLink.name" class="footer-content__bottom-links__item">
            <a :href="socialLink.url" target="_blank">
              {{ socialLink.name }}
            </a>
          </li>
        </ul>
      </div>
    </section>
  </footer>
</template>

<style scoped>
#footer {
  min-height: 900px;
  background-color: var(--lilac-color);
  padding: 140px 112px 30px 112px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.footer-content {
  height: 100%;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.footer-content__top {
  display: flex;
  gap: 368px;
  flex-grow: 1;
}

.footer-content__top-left__sub {
  font-size: 16px;
  line-height: 120%;
  margin-bottom: 56px;
}

.footer-content__top-left__cap {
  font-size: 112px;
  max-width: 464px;
  width: 100%;
  line-height: 100%;
  text-decoration: underline;
  text-decoration-thickness: 2px;
  text-underline-offset: 10px;
}

.footer-content__top-right {
  margin-top: 75px;
}

.footer-content__top-right__item {
  margin-bottom: 36px;
  max-width: 152px;
}

.footer-content__top-right__item:last-child {
  margin-bottom: 0;
}

.footer-content__top-right__item-title {
  font-size: 16px;
  line-height: 120%;
  margin-bottom: 12px;
}

.footer-content__top-right__item-content {
  font-size: 16px;
  line-height: 120%;
  margin-bottom: 4px;
}

.footer-content__top-right__item-content:last-child {
  margin-bottom: 0;
}

.footer-content__top-right__item-link {
  width: 32px;
  height: 32px;
  border-radius: 100%;
  background-color: var(--black-color);
}

.footer-content__top-right__item-link > a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.footer-content__top-right__item-link > a > svg {
  width: 12px;
}

.footer-content__bottom {
  margin-top: auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.footer-content__bottom-links {
  display: flex;
  align-items: center;
  gap: 32px;
  margin-right: 704px;
}

.footer-content__bottom-links:last-child {
  margin-right: 0;
}

.footer-content__bottom-links__item > a {
  font-size: 16px;
  line-height: 120%;
  text-decoration: underline;
  text-underline-offset: 6px;
}

.footer-content__bottom-btn {
  position: absolute;
  cursor: pointer;
  width: 358px;
  height: 358px;
  background: var(--black-color);
  color: var(--white-color);
  left: 50%;
  top: -120px;
  transform: translate(-50%);
  border-radius: 100%;
}

.footer-content__bottom-btn__text {
  font-size: 32px;
  display: block;
  width: 38px;
  line-height: 100%;
  margin: 120px auto 0 auto;
}
</style>

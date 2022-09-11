<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper'
// composable
// const { t } = useLang()

// meta
definePageMeta({
  layout: 'page',
})
</script>

<template>
  <PageWrapper>
    <PageBody>
      <PageSection>
        <Swiper
          :slides-per-view="1"
          :modules="[Autoplay]"
          :autoplay="{
            delay: 2500,
            disableOnInteraction: false,
          }"
        >
          <SwiperSlide>
            <img
              src="https://f2.kkmh.com/image/220908/Ne8PwQbsW.png-t.w1125.png.h"
              alt=""
            />
          </SwiperSlide>
          <SwiperSlide>
            <img
              src="https://f2.kkmh.com/image/220901/Jyn6KWC2H.png-t.w1125.png.h"
              alt=""
            />
          </SwiperSlide>
          <SwiperSlide>
            <img
              src="https://f2.kkmh.com/image/220908/Ne8PwQbsW.png-t.w1125.png.h"
              alt=""
            />
          </SwiperSlide>
        </Swiper>
      </PageSection>
    </PageBody>
  </PageWrapper>
</template>

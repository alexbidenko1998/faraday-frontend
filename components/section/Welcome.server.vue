<script lang="ts" setup>
import hardox from '~/assets/icons/hardox.svg?url';
import verticalHardox from '~/assets/icons/vertical_hardox.svg?url';
import background from '~/assets/images/welcome_section_background.jpg';
</script>

<template>
  <section class="sectionWelcome">
    <NuxtImg
      :src="background"
      :sizes="IMAGE_SIZES.fullscreen"
      alt="Фон сайта Фарадей"
      class="sectionWelcome__background"
    />
    <div class="sectionWelcome__shadow" />

    <div class="sectionWelcome__content container">
      <div class="sectionWelcome__info">
        <h1 class="sectionWelcome__title">ФАРАДЕЙ</h1>
        <p class="sectionWelcome__slogan">«Стоп Износ»</p>
        <NuxtLink to="/#request">
          <BaseButton size="l"> Оставить заявку </BaseButton>
        </NuxtLink>
      </div>

      <div class="sectionWelcome__banner">
        <picture>
          <source media="(max-width: 1024px)" :srcset="verticalHardox" />
          <img
            :src="hardox"
            alt="Надпись HARDOX"
            class="sectionWelcome__hardox"
          />
        </picture>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.sectionWelcome {
  height: 100vh;
  overflow: hidden;

  &__background {
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  &__shadow {
    background: linear-gradient(
      180deg,
      #0a363c 22.34%,
      rgba(10, 54, 60, 0) 100%
    );
    opacity: 0.7;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 35.5%;
  }

  &__content {
    position: relative;
    height: 100%;
    display: flex;
    align-items: center;
    gap: var(--grid-gap);
  }

  &__info {
    padding-top: 143px;
    flex: 1;

    @include mq('xl') {
      padding-top: 140px;
    }
  }

  &__title {
    font-weight: 700;
    font-size: 64px;
    line-height: 77px;
    color: #111112;
    margin-top: 0;
    margin-bottom: 32px;

    @include mq('xl') {
      font-size: 48px;
      line-height: 58px;
    }
  }

  &__slogan {
    font-size: 32px;
    line-height: 39px;
    color: #111112;
    margin-top: 0;
    margin-bottom: 86px;

    @include mq('xl') {
      font-size: 24px;
      line-height: 29px;
      margin-bottom: 84px;
    }
  }

  &__banner {
    padding-top: 60px;
    flex: 1;

    @include mq('xl') {
      padding-top: 42px;
    }
  }

  &__hardox {
    margin-left: auto;
    display: block;
    width: 668px;
    height: 188px;

    @include mq('xxl') {
      width: 476px;
      height: 134px;
    }

    @include mq('md') {
      width: 141px;
      height: 503px;
      transform: translateX(calc(24px + var(--container-padding)));
    }
  }
}
</style>

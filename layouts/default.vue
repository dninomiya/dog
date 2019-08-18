<template>
  <div>
    <header class="header" :class="{ 'drawer-is-open': isDrawerOpen }">
      <a class="header__menu-trg" @click="isDrawerOpen = true">
        menu
      </a>
      <p class="header__title">
        <nuxt-link to="/">Nuxt Demo</nuxt-link>
      </p>
      <ul class="gnav">
        <li class="gnav__item">
          <nuxt-link to="/about" class="gnav__link">About</nuxt-link>
        </li>
        <li class="gnav__item">
          <nuxt-link to="/services" class="gnav__link">Services</nuxt-link>
        </li>
        <li class="gnav__item">
          <nuxt-link to="/staff" class="gnav__link">Staff</nuxt-link>
        </li>
        <li class="gnav__item">
          <nuxt-link to="/contact" class="gnav__link">Contact</nuxt-link>
        </li>
      </ul>
      <div class="drawer-overlay" @click="isDrawerOpen = false"></div>
    </header>
    <nuxt />
    <footer class="footer">
      <p class="footer__copyright">&copy; Nino Labo.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDrawerOpen: false
    }
  }
}
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  padding: 16px;
  border-bottom: 1px solid rgba(black, 0.12);
  &__menu-trg {
    display: none;
    @include sp {
      display: block;
    }
  }
  &__title {
    font-size: 16px;
  }
}

.gnav {
  display: flex;
  &__link {
    padding: 8px;
    display: inline;
    &.nuxt-link-active {
      font-weight: bold;
    }
  }
  @include sp {
    position: fixed;
    background: #fff;
    display: block;
    top: 0;
    left: 0;
    bottom: 0;
    z-index: 10;
    width: 240px;
    transition: 0.3s;
    transform: translateX(-100%);
    .drawer-is-open & {
      transform: translateX(0);
    }
  }
}

.drawer-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #000;
  opacity: 0;
  transition: 0.3s;
  visibility: hidden;
  .drawer-is-open & {
    visibility: visible;
    opacity: 0.8;
  }
}

.footer {
  padding: 16px;
  text-align: center;
  font-size: 12px;
}
</style>

<template>
  <div>
    <header class="header">
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
    </header>
    <nuxt />
    <footer class="footer">
      <p class="footer__copyright">&copy; Nino Labo.</p>
    </footer>
  </div>
</template>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  padding: 16px;
  border-bottom: 1px solid rgba(black, 0.12);
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
}

.footer {
  padding: 16px;
  text-align: center;
  font-size: 12px;
}
</style>

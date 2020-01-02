<template>
  <div class="container">
    <b-navbar>
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/'}">
          <g-image alt="Example image" src="~/favicon.png" width="25" />
        </b-navbar-item>
      </template> -->
      <template slot="start">
        <b-navbar-item tag="router-link" :to="{ path: '/'}">
          Home
        </b-navbar-item>
        <b-navbar-item tag="router-link" :to="{ path: '/about/'}"> 
          About
        </b-navbar-item>
        <b-navbar-dropdown label="Shop">
          <b-navbar-item>
            Gameboy
          </b-navbar-item>
          <b-navbar-item>
            Merch
          </b-navbar-item>
        </b-navbar-dropdown>
      </template>
      <template slot="end">
        <b-navbar-item>
          Cart
        </b-navbar-item>
        <b-navbar-item>
          Log in
        </b-navbar-item>
      </template>
    </b-navbar>
    <slot/>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>

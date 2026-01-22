<template>
  <nav class="navbar navbar-expand-lg shadow-sm bg-white">
    <div class="container">
      <!-- LOGO -->
      <router-link class="navbar-brand fw-bold" to="/">
        🏢 TEH
      </router-link>

      <!-- TOGGLER -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#tehNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- MENU -->
      <div class="collapse navbar-collapse" id="tehNavbar">
        <ul class="navbar-nav ms-auto align-items-lg-center">
          <li class="nav-item">
            <router-link class="nav-link" to="/">
              Trang chủ
            </router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/about">
              Giới thiệu
            </router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/projects">
              Dự án
            </router-link>
          </li>

          <li class="nav-item">
            <router-link class="nav-link" to="/login">
              Đăng nhập
            </router-link>
          </li>

          <li class="nav-item ms-lg-2">
            <router-link class="btn btn-green" to="/register">
              Đăng ký
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar-brand {
  color: var(--green-main) !important;
}

.nav-link {
  color: var(--text-main) !important;
  font-weight: 500;
}

.nav-link:hover {
  color: var(--green-main) !important;
}
</style>

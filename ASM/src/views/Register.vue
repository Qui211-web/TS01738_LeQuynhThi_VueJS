<template>
  <div class="register-page">
    <div class="container d-flex justify-content-center align-items-center">
      <div class="card register-card p-4">
        <h4 class="text-center mb-4 text-green fw-bold">
          Đăng ký tài khoản TEH
        </h4>

        <div class="mb-3">
          <label class="form-label">Họ và tên</label>
          <input
            type="text"
            class="form-control"
            placeholder="Nhập họ và tên"
          />
        </div>

        <div class="mb-3">
          <label class="form-label">Email</label>
          <input
            type="email"
            class="form-control"
            placeholder="example@email.com"
          />
        </div>

        <div class="mb-3">
          <label class="form-label">Mật khẩu</label>
          <input
            type="password"
            class="form-control"
            placeholder="Nhập mật khẩu"
          />
        </div>

        <div class="mb-3">
          <label class="form-label">Xác nhận mật khẩu</label>
          <input
            type="password"
            class="form-control"
            placeholder="Nhập lại mật khẩu"
          />
        </div>

        <button class="btn btn-green w-100 mb-3">
          Đăng ký
        </button>

        <p class="text-center mb-0">
          Đã có tài khoản?
          <router-link to="/login" class="text-green fw-semibold">
            Đăng nhập
          </router-link>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.register-page {
  min-height: calc(100vh - 70px);
  background: linear-gradient(135deg, #e8fff7, #f6fffc);
  padding-top: 60px;
}

.register-card {
  width: 420px;
  border-radius: 14px;
  border: none;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.text-green {
  color: #1fa37c;
}

.btn-green:hover {
  background-color: #178d6a;
}
</style>
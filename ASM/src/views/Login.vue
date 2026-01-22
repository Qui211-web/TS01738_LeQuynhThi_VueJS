<template>
  <div class="login-page">
    <div class="card login-card shadow">
      <h3 class="text-center mb-4 brand">TEH REAL ESTATE</h3>

      <div class="mb-3">
        <label class="form-label">Email</label>
        <input
          v-model="email"
          type="email"
          class="form-control"
          placeholder="example@email.com"
        />
      </div>

      <div class="mb-3">
        <label class="form-label">Mật khẩu</label>
        <input
          v-model="password"
          type="password"
          class="form-control"
          placeholder="••••••••"
        />
      </div>

      <div v-if="error" class="alert alert-danger py-2">
        {{ error }}
      </div>

      <button class="btn btn-teh w-100" @click="login">
        Đăng nhập
      </button>

      <p class="text-center mt-3 mb-0">
        Chưa có tài khoản?
        <router-link to="/register">Đăng ký</router-link>
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const email = ref('')
const password = ref('')
const error = ref('')
const router = useRouter()

const login = () => {
  if (!email.value || !password.value) {
    error.value = 'Vui lòng nhập đầy đủ thông tin'
    return
  }

  // Giả lập đăng nhập (Y1 – Y2)
  const user = {
    email: email.value,
    name: 'Người dùng TEH'
  }

  localStorage.setItem('user', JSON.stringify(user))
  router.push('/')
}
</script>

<style scoped>
.login-page {
  min-height: 100vh;
  background: linear-gradient(135deg, #e8f5f2, #f1fbf9);
  display: flex;
  align-items: center;
  justify-content: center;
}

.login-card {
  width: 380px;
  padding: 28px;
  border-radius: 16px;
  background-color: #ffffff;
}

.brand {
  font-weight: 700;
  color: #1b8f7a;
  letter-spacing: 1px;
}

.btn-teh {
  background-color: #1b8f7a;
  color: #fff;
  border-radius: 10px;
  font-weight: 500;
}

.btn-teh:hover {
  background-color: #157564;
}
</style>

<script setup>
import p1 from '../assets/projects/project1.jpg'
import p2 from '../assets/projects/project2.jpg'
import p3 from '../assets/projects/project3.jpg'


const projects = [
  {
    id: 1,
    name: 'TEH Green City',
    address: 'Quận 9 – TP.HCM',
    price: '3,2 tỷ VNĐ',
    image: p1
  },
  {
    id: 2,
    name: 'TEH Riverside',
    address: 'Quận 7 – View sông',
    price: '4,8 tỷ VNĐ',
    image: p2
  },
  {
    id: 3,
    name: 'TEH Smart Living',
    address: 'Thủ Đức – Khu công nghệ cao',
    price: '2,9 tỷ VNĐ',
    image: p3
  }
]
</script>

<template>
  <div class="container mt-5">
   <div class="section-header text-center mb-5">
  <div class="icon-box mb-3">
    <i class="bi bi-building"></i>
  </div>

  <h2 class="section-title">
    Dự án nổi bật
  </h2>

  <h4 class="section-brand">
    TEH Real Estate
  </h4>

  <p class="section-subtitle">
    Kiến tạo không gian sống bền vững & giá trị lâu dài
  </p>
</div>


    <div class="row g-4">
      <div
        class="col-md-4"
        v-for="item in projects"
        :key="item.id"
      >
        <div class="card h-100 project-card">
          <img
            :src="item.image"
            class="card-img-top project-img"
            alt="Project image"
          />

          <div class="card-body d-flex flex-column">
            <h5 class="card-title">{{ item.name }}</h5>
            <p class="text-muted mb-1">{{ item.address }}</p>
            <p class="price mb-3">{{ item.price }}</p>

            <router-link
              :to="`/post/${item.id}`"
              class="btn btn-green mt-auto"
            >
              Xem chi tiết
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.section-title {
  font-weight: 700;
  color: #0f5132;
}

/* Ảnh đều nhau */
.project-img {
  height: 220px;
  width: 100%;
  object-fit: cover;
}

/* Card nổi bật hơn */
.project-card {
  border-radius: 14px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 14px 32px rgba(0, 0, 0, 0.15);
}

.price {
  font-weight: 600;
  color: #198754;
}

/* Nút xanh thương hiệu */
.btn-green {
  background-color: #198754;
  color: white;
  border-radius: 8px;
}

.btn-green:hover {
  background-color: #157347;
}
</style>

<template>
  <div class="container mt-5" style="max-width: 900px">

    <!-- THÔNG TIN DỰ ÁN -->
    <div class="card p-4 mb-4">
      <h3 class="mb-2">{{ post.title }}</h3>
      <p class="text-muted">{{ post.location }}</p>

      <img :src="post.image" class="img-fluid rounded mb-3" />

      <p>{{ post.description }}</p>
      <p class="fw-bold text-success">{{ post.price }}</p>
    </div>

    <!-- COMMENT -->
    <div class="card p-4">
      <h5 class="mb-3">Bình luận</h5>

      <!-- CHƯA ĐĂNG NHẬP -->
      <div v-if="!user" class="alert alert-warning">
        Bạn cần <router-link to="/login">đăng nhập</router-link> để bình luận
      </div>

      <!-- ĐÃ ĐĂNG NHẬP -->
      <div v-else class="mb-3">
        <textarea
          v-model="comment"
          class="form-control mb-2"
          rows="3"
          placeholder="Nhập bình luận của bạn..."
        ></textarea>

        <button class="btn btn-success" @click="submitComment">
          Gửi bình luận
        </button>
      </div>

      <!-- DANH SÁCH COMMENT -->
      <div v-if="comments.length === 0" class="text-muted">
        Chưa có bình luận nào
      </div>

      <ul class="list-group mt-3">
        <li
          class="list-group-item"
          v-for="(c, index) in comments"
          :key="index"
        >
          <strong>{{ c.author }}</strong>
          <div>{{ c.content }}</div>
        </li>
      </ul>
    </div>

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const postId = route.params.id

/* ===== USER ===== */
const user = ref(null)

/* ===== POST DATA (GIẢ LẬP) ===== */
const post = ref({
  title: 'TEH Riverside',
  location: 'Quận 7 – View sông',
  price: '4,8 tỷ VNĐ',
  image: 'https://picsum.photos/900/400',
  description:
    'Dự án bất động sản cao cấp ven sông, không gian xanh, phù hợp gia đình trẻ.'
})

/* ===== COMMENT ===== */
const comment = ref('')
const comments = ref([])

/* ===== LOAD DATA ===== */
onMounted(() => {
  // Load user
  const savedUser = localStorage.getItem('user')
  user.value = savedUser ? JSON.parse(savedUser) : null

  // Load comment theo postId
  const savedComments = localStorage.getItem(`comments_${postId}`)
  comments.value = savedComments ? JSON.parse(savedComments) : []
})

/* ===== SUBMIT COMMENT ===== */
const submitComment = () => {
  if (!user.value) {
    alert('Bạn chưa đăng nhập')
    return
  }

  if (!comment.value.trim()) return

  comments.value.push({
    author: user.value.name,
    content: comment.value
  })

  localStorage.setItem(
    `comments_${postId}`,
    JSON.stringify(comments.value)
  )

  comment.value = ''
}
</script>

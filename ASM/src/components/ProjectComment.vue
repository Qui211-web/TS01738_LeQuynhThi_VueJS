<template>
  <div class="mt-5">
    <h5 class="section-title mb-3">Bình luận</h5>

    <!-- CHƯA LOGIN -->
    <div v-if="!user" class="alert alert-warning">
      Vui lòng <router-link to="/login">đăng nhập</router-link> để bình luận.
    </div>

    <!-- ĐÃ LOGIN -->
    <div v-else>
      <textarea
        v-model="newComment"
        class="form-control mb-2"
        placeholder="Nhập bình luận..."
      ></textarea>

      <button class="btn btn-green mb-4" @click="addComment">
        Gửi bình luận
      </button>
    </div>

    <!-- DANH SÁCH COMMENT -->
    <div
      v-for="(cmt, index) in comments"
      :key="index"
      class="p-3 mb-3 bg-white rounded shadow-sm"
    >
      <strong>{{ cmt.user }}</strong>
      <p class="mb-1">{{ cmt.content }}</p>
      <small class="text-muted">{{ cmt.time }}</small>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  projectId: {
    type: Number,
    required: true
  }
})

const user = JSON.parse(localStorage.getItem('user'))
const comments = ref([])
const newComment = ref('')

const storageKey = `comments_project_${props.projectId}`

onMounted(() => {
  comments.value =
    JSON.parse(localStorage.getItem(storageKey)) || []
})

const addComment = () => {
  if (!newComment.value) return

  comments.value.push({
    user: user.name,
    content: newComment.value,
    time: new Date().toLocaleString()
  })

  localStorage.setItem(
    storageKey,
    JSON.stringify(comments.value)
  )

  newComment.value = ''
}
</script>

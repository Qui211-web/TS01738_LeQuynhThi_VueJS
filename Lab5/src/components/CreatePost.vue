<template>
  <div class="p-3 border rounded mb-4">
    <h3>Tạo bài viết mới</h3>

    <div class="mb-2">
      <input
        v-model="title"
        type="text"
        class="form-control"
        placeholder="Tiêu đề"
      />
    </div>

    <div class="mb-2">
      <input
        v-model="author"
        type="text"
        class="form-control"
        placeholder="Tác giả"
      />
    </div>

    <div class="mb-2">
      <textarea
        v-model="content"
        class="form-control"
        placeholder="Nội dung"
      ></textarea>
    </div>

    <button class="btn btn-dark" @click="addPost">
      Thêm bài viết
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const emit = defineEmits(['add-post']);

const title = ref('');
const author = ref('');
const content = ref('');

const addPost = () => {
  emit('add-post', {
    title: title.value,
    author: author.value,
    content: content.value
  });

  title.value = '';
  author.value = '';
  content.value = '';
};
</script>

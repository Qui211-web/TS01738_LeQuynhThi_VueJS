<!-- Bai1 -->
 <!-- <template>
  <div class="p-5">
    <p>{{ message }}</p>
    <button class="btn btn-dark" @click="updateMessage">
      Thay đổi thông điệp
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const message = ref('Thông điệp ban đầu');

const updateMessage = () => {
  message.value = 'Thông điệp đã được thay đổi!';
};
</script> -->


<!-- Bai2 -->
 <!-- <template>
  <div>
    <input v-model="userInput" placeholder="Nhập dữ liệu vào đây" />
    <p>Giá trị bạn nhập: {{ userInput }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const userInput = ref('FPL');
</script> -->


<!-- Bai3 -->
<template>
  <div class="col-sm-8">
    <h1>Thông tin cá nhân</h1>

    <form>
      <div class="mb-3">
        <label>Họ và Tên:</label>
        <input
          v-model="userInfo.name"
          type="text"
          class="form-control"
          placeholder="Nhập họ và tên"
        />
      </div>

      <div class="mb-3">
        <label>Tuổi:</label>
        <input
          v-model="userInfo.age"
          type="number"
          class="form-control"
          placeholder="Nhập tuổi"
        />
      </div>

      <div class="mb-3">
        <label>Email:</label>
        <input
          v-model="userInfo.email"
          type="email"
          class="form-control"
          placeholder="Nhập email"
        />
      </div>
    </form>

    <div class="info-display mt-4 p-3 bg-dark text-white rounded">
      <h2>Thông tin đã nhập:</h2>
      <p><strong>Họ và Tên:</strong> {{ userInfo.name }}</p>
      <p><strong>Tuổi:</strong> {{ userInfo.age }}</p>
      <p><strong>Email:</strong> {{ userInfo.email }}</p>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue';

const userInfo = reactive({
  name: '',
  age: null,
  email: ''
});
</script>


<!-- Bai4 -->
 <!-- <template>
  <div class="container mt-4">
    <CreatePost @add-post="addPost" />
    <PostList :posts="posts" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import CreatePost from './components/CreatePost.vue';
import PostList from './components/PostList.vue';

const posts = ref([]);

const addPost = (post) => {
  posts.value.push(post);
};
</script> -->


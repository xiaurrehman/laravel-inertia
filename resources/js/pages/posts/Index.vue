<template>
  <div class="max-w-6xl mx-auto mt-10 px-4">
    <div class="flex justify-between items-center mb-6">
      <h1 class="text-2xl font-bold text-white-800">My Inertia CRUD</h1>
      <Link
        href="/posts/create"
        class="inline-flex items-center gap-2 rounded-lg bg-blue-600 px-4 py-2 text-white font-semibold hover:bg-blue-700 transition duration-150"
      >
        <PlusIcon class="h-5 w-5" />
        Create New Post
      </Link>
    </div>

    <div class="overflow-x-auto bg-white shadow rounded-xl">
      <table class="min-w-full divide-y divide-gray-200">
        <thead class="bg-gray-50 text-left text-sm font-semibold text-gray-600">
          <tr>
            <th class="px-6 py-3">ID</th>
            <th class="px-6 py-3">Title</th>
            <th class="px-6 py-3">Content</th>
            <th class="px-6 py-3">Actions</th>
          </tr>
        </thead>
        <tbody class="divide-y divide-gray-100 text-sm text-gray-700">
          <tr
            v-for="post in posts"
            :key="post.id"
            class="hover:bg-gray-50 transition duration-100"
          >
            <td class="px-6 py-4">{{ post.id }}</td>
            <td class="px-6 py-4">{{ post.title }}</td>
            <td class="px-6 py-4">{{ post.content }}</td>
            <td class="px-6 py-4 flex gap-3">
                <Link
                    :href="`posts/${post.id}/edit`"
                    class="text-blue-600 hover:text-blue-800 font-medium inline-flex items-center gap-1"
                >
                    <PencilSquareIcon class="h-5 w-5" />
                    Edit
                </Link>

                <button
                    @click="deletePost(post.id)"
                    class="text-red-600 hover:text-red-800 font-medium inline-flex items-center gap-1"
                >
                    <TrashIcon class="h-5 w-5" />
                    Delete
                </button>
            </td>

          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup>
import { Link, useForm } from "@inertiajs/vue3";

// Import heroicons from @heroicons/vue
import {  
    PlusIcon, 
    TrashIcon, 
    PencilSquareIcon } from "@heroicons/vue/24/solid"; // or `/outline` if you prefer

defineProps({
  posts: {
    type: Array,
    default: () => [],
  },
});

const form = useForm({});

const deletePost = (id) => {
  if (confirm("Are you sure you want to delete this post?")) {
    form.delete(`/posts/${id}`);
  }
};
</script>

<style scoped></style>

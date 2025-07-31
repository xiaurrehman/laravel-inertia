<template>
  <div class="max-w-xl mx-auto mt-10 bg-white p-8 rounded-2xl shadow-lg">
    <h2 class="text-xl font-bold text-gray-800 mb-6 flex items-center gap-2">
      <PencilSquareIcon class="h-6 w-6 text-blue-600" />
      Create New Post
    </h2>

    <form @submit.prevent="submit" class="space-y-6">
      <!-- Title -->
      <div>
        <label for="title" class="block text-sm font-medium text-gray-700 mb-1">
          Title
        </label>
        <div class="relative">
          <input
            type="text"
            id="title"
            v-model="form.title"
            placeholder="Enter post title"
            class="w-full rounded-lg border border-gray-300 bg-white text-gray-800 px-4 py-2 pl-10 text-sm shadow-sm focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50 focus:outline-none"
          />
          <span class="absolute left-3 top-2.5 text-gray-400">
            <DocumentTextIcon class="h-5 w-5" />
          </span>
        </div>
      </div>

      <!-- Content -->
      <div>
        <label for="content" class="block text-sm font-medium text-gray-700 mb-1">
          Content
        </label>
        <div class="relative">
          <textarea
            id="content"
            v-model="form.content"
            rows="4"
            placeholder="Enter post content"
            class="w-full rounded-lg border border-gray-300 bg-white text-gray-800 px-4 py-2 pl-10 text-sm shadow-sm focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50 focus:outline-none"
          ></textarea>
          <span class="absolute left-3 top-2.5 text-gray-400">
            <ChatBubbleLeftRightIcon class="h-5 w-5" />
          </span>
        </div>
      </div>

      <!-- Submit -->
      <div class="flex justify-end">
        <button
          type="submit"
          class="inline-flex items-center gap-2 rounded-lg bg-blue-600 px-5 py-2 text-white font-semibold hover:bg-blue-700 transition duration-150"
        >
          <PaperAirplaneIcon class="h-5 w-5 rotate-45 text-white" />
          Add Post
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";
import {
  ChatBubbleLeftRightIcon,
  DocumentTextIcon,
  PencilSquareIcon,
  PaperAirplaneIcon,
} from "@heroicons/vue/24/solid";

const form = useForm({
  title: "",
  content: "",
});

const submit = () => form.post("/posts");
</script>

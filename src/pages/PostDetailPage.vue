<template>
    <section class="page">
        <div class="breadcrumb">
            <RouterLink to="/posts">← Back to Posts</RouterLink>
        </div>

        <h1>{{ title }}</h1>
        <p class="muted">slug：{{ slug }}</p>

        <article class="article">
            <p>這裡是文章內容示例。下一步可以改成讀 JSON 或 Markdown。</p>
        </article>
    </section>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{ slug: string }>()

const title = computed(() =>
    props.slug
        .split('-')
        .map((s) => s[0]?.toUpperCase() + s.slice(1))
        .join(' ')
)
</script>

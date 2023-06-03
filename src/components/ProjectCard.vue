<script setup>
import IconArrow from './icons/IconArrow.vue'
</script>

<template>
    <div class="project-card">
        <div class="left">
            <img :src="`/images/${imgName}`" class="project-image">
        </div>
        <div class="right">
            <div class="main">
                <a :href="link" target="_blank"><h3 class="name">{{ name }}</h3></a>
                <IconArrow class="icon"></IconArrow>
            </div>
            <p class="description">{{ description }}</p>
            <div class="technologies">
                <span v-for="tech in techs" class="tech">
                    {{ tech }}
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    imgName: String,
    name: String,
    link: String,
    description: String,
    techs: Array,
  }
}
</script>

<style scoped>
.project-card {
    display: flex;
    gap: 2rem;
    color: #e6edf8;
}

.project-image {
    border-radius: 0.5rem;
    width: 7rem;
    height: 3.5rem;
}

.main {
    display: flex;
    gap: 0.35rem;
}

.icon {
    width: 1.2rem;
}

.name {
    font-size: 1.2rem;
    line-height: normal;
    font-weight: 600;
}

a {
    all: unset;
}

a:hover {
    cursor: pointer;
    text-decoration: underline;
}

.technologies {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
}

.tech {
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    background-color: rgba(94, 234, 213, 0.07);
}

.left {
    width: 9rem;
}

.right {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
}
</style>

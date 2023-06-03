<script setup>

</script>

<template>
    <div class="contents">
        <div @click="$emit('scrollto', 'about')" class="content-item" :class="{ active: section === 0 }">
            About
        </div>
        <div @click="$emit('scrollto', 'experience')" class="content-item" :class="{ active: section === 1 }">
            Experience
        </div>
        <div @click="$emit('scrollto', 'education')" class="content-item" :class="{ active: section === 2 }">
            Education
        </div>
        <div @click="$emit('scrollto', 'projects')" class="content-item" :class="{ active: section === 3 }">
            Projects
        </div>
    </div>
</template>

<script>
export default {
  props: {
    section: Number
  }
}
</script>

<style scoped>
 .contents {
    display: flex;
    flex-direction: column;
    gap: 1rem;
 }

 .content-item {
    color: #95bae4;
    font-size: 1.5rem;
    width: fit-content;
 }

 .content-item:hover {
    color: #3879bf;
    cursor: pointer;
 }

 .active {
    color: #c7daf0;
    text-decoration: underline;
 }
</style>

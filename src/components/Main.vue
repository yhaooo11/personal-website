<script setup>
    import image from "../assets/YifanHao.jpeg"
</script>

<template>
    <div class="header">
        <img class="avatar" :src="image" />
        <div>
            <h1>Yifan Hao</h1>
            <h2>SWE Intern @ Sony Pictures Imageworks</h2>
            <h2>CS + Stats Student @ UBC</h2>
        </div>
    </div>
</template>

<script>
</script>

<style scoped>
.header {
    display: flex;
    gap: 3rem;
}

@media (max-width: 1000px) {
  .header {
    flex-direction: column;
  }
}

.avatar {
    border-radius: 50%;
    aspect-ratio: 1 / 1;
    width: 12rem;
}

@media (max-width: 1000px) {
  .avatar {
    width: 10rem;
  }
}

.about {
    color: #e6edf8;
}

a {
    all: unset;
}

a:hover {
    cursor: pointer;
}

h1 {
    color: #c7daf0;
    font-weight: 800;
    font-size: 3rem;
    margin-bottom: 0.8rem;
}

h2 {
    color: #c7daf0;
    font-size: 1.2rem;
    font-weight: 500;
}
</style>

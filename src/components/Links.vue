<script setup>
import IconGithub from './icons/IconGithub.vue';
import IconLinkedin from './icons/IconLinkedin.vue';
import IconMail from './icons/IconMail.vue';
</script>

<template>
    <div class="links">
        <a class="link-icon" target="_blank" href="https://github.com/yhaooo11">
            <IconGithub></IconGithub>
        </a>
        <a class="link-icon" target="_blank" href="https://www.linkedin.com/in/yifan-hao03/">
            <IconLinkedin></IconLinkedin>
        </a>
        <a class="link-icon" href="mailto:yifanhao5@gmail.com">
            <IconMail></IconMail>
        </a>
    </div>
</template>

<script>
</script>

<style scoped>
.links {
    display: flex;
    gap: 1.5rem;
}
.link-icon {
    width: 1.5rem;
    color: #f3f6fc;
}

.link-icon:hover {
    cursor: pointer;
}

a {
    all: unset;
}
</style>

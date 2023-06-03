<template>
    <div class="experience-card">
        <div class="left">
            <span class="date">{{ startDate }} - {{ endDate }}</span>
        </div>
        <div class="right">
            <div>
                <h3 class="role">{{ role }}</h3>
                <h4 class="company">
                    <a href="https://verto.health/" target="_blank">{{ company }}</a>
                </h4>
            </div>
            <p class="description">{{ description }}</p>
            <div class="skills">
                <span v-for="skill in skills" class="skill">
                    {{ skill }}
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    startDate: String,
    endDate: String,
    role: String,
    company: String,
    description: String,
    skills: Array,
  }
}
</script>

<style scoped>
.experience-card {
    display: flex;
    gap: 2rem;
    color: #e6edf8;
}

a {
    all: unset;
}

a:hover {
    cursor: pointer;
}

.date {
    color: rgb(100 116 139);
    font-weight: 600;
    font-size: 1rem;
}

.role {
    font-size: 1.2rem;
    line-height: normal;
    font-weight: 600;
}

.company {
    font-size: 1.1rem;
    font-weight: 500;
}

.skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
}

.skill {
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

<template>
    <div class="education-card">
        <div class="left">
            <span class="date">{{ gradDate }}</span>
        </div>
        <div class="right">
            <div>
                <h3 class="school">{{ school }}</h3>
                <h4 class="degree">
                    {{ degree }}
                </h4>
            </div>
            <p>GPA: {{ gpa }}</p>
            <p class="description">{{ description }}</p>
            <div class="relevant-courses">
                <span class="relev-text">Relevant Courses: </span>
                <span v-for="course in relevantCourses" class="relevantCourse">
                    {{ course }}
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    gradDate: String,
    school: String,
    degree: String,
    gpa: String,
    relevantCourses: Array,
  }
}
</script>

<style scoped>
.education-card {
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

.school {
    font-size: 1.2rem;
    line-height: normal;
    font-weight: 600;
}

.degree {
    font-size: 0.95rem;
    font-weight: 500;
}

.relevant-courses {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-top: 1rem;
}

.relevantCourse {
    padding: 0.25rem 0.75rem;
    border-radius: 1rem;
    background-color: rgba(94, 234, 213, 0.07);
}

.relev-text {
    font-size: 1.1rem;
}

.left {
    width: 10rem;
}

.right {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 0.2rem;
}
</style>

<template>
    <div class="home">
        <img alt="logo" class="mb-4" src="../assets/quiz.jpg" />
        <quizs />
    </div>
</template>

<script>
import Quizs from "@/components/Quizs.vue";

export default {
    name: "home",
    components: {
        Quizs,
    },
};
</script>
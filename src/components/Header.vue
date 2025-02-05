<template>
    <header>
        <h1>{{title}}</h1>
        <Button 
            v-show="isHomePage"
            :text="showAddTask ? 'Close' : 'Add Task'" 
            @btn-click="$emit('toggle-add-task')" 
            :color="showAddTask ? 'red' : 'green' "
        />
    </header>
</template>

<script>
import Button from "./Button.vue";
export default {
    name: "Header",
    props: {
        title: String,
        showAddTask: Boolean
    },
    emits: [
        'btn-click'
    ],
    components: { Button },
    computed: {
        isHomePage() {
            return this.$route.path === '/'
        }
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>
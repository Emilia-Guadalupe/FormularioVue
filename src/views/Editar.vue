<template>
    <form @submit.prevent="updateTask(edit)">
        <Inputs :tarea="edit" />
    </form>
</template>

<script>
import {mapState, mapActions} from 'vuex';
import Inputs from '../components/Inputs';
export default {
    components: {
        Inputs
    },
    computed: {
        ...mapState(['edit'])
    },
    methods: {
        ...mapActions(['setTask', 'updateTask'])
    },
    created(){
        this.setTask(this.$route.params.id)
    }
}
</script>


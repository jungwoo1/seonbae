<template>
    <div>
        
        <p v-for="item in this.$store.state.jobs">
        <a v-bind:href="item.url">
            {{item.title}}</a>
            <small>{{item.time_ago}},{{item.domain}}</small>
            </p>
    </div>
</template>

<script> 
import { mapState } from 'vuex'
export default {
    computed: {
        ...mapState({
            ask: state => state.ask
        })
    },
    
    created() {
        this.$store.dispatch('FETCH_ASK')
      
    },
}
</script>

<style scoped>

</style>
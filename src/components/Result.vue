<template>
    <div>
        <p>time:{{this.score}}</p>
        <p>{{this.rank}}</p>
    </div>
</template>
<script>
export default {
    props: ['score'],
    data(){
        return{
        rank: null
    }

    },
    mounted() {
        if(this.score < 250){
            this.rank = "fast pace"
        }
        if (this.score <600) {
            this.rank = "medium pace"
        } else {
            this.rank = "snail pace"
        }
    },

}
</script>
<template>
    <div class="Block" v-if="showChange" @click="stop">
        click
    </div>

</template>

<script>
export default{
    props:['delay'],
    data(){
        return{
            showChange: false,
            startCounter :null,
            stopCounter :0
        }
    },
    mounted(){
        setTimeout(() =>{
            this.showChange = true
            this.startTimer()
        }, this.delay)
        
    }, 
    methods:{
        startTimer(){
            this.startCounter= setInterval(()=>{
                this.stopCounter+= 10
            }, 10)
        },
        stop(){
            clearInterval(this.startCounter)
            console.log(this.stopCounter)
            this.$emit('end', this.stopCounter)
        },
    }
}        
</script>
<style>
.Block{
    width: 400px;
    border-radius: 20px;
    background: green;
    color: white;
    text-align: center;
    padding:100px 0;
    margin:40px auto;
}
</style>
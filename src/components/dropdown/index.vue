<template>
    <div>
        <span @mouseenter="hover($event,index)" @mouseleave="hover($event,-1)" v-for="(item,index) in data" :key="index">{{item}}</span>
    </div>
</template>

<script>
export default {
    props:{
        data:{
            type:Array,
            default:() => []
        }
    },
    methods:{
        hover(e,index){
            // console.log(111)
            this.$emit('cur-hover', index)
        },
    }
}
</script>

<style scoped>
span{
    border:1px solid #000;
    margin-right:10px;
    cursor: pointer;
}
</style>

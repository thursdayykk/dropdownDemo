<template>
    <transition name="el-zoom-in-top">
        <ul v-show="cur != -1">
            <li v-for="(item,index) in menu[cur]" :key="index">{{item}}</li>
        </ul>
    </transition>
</template>

<script>
export default {
    props:{
        menu:{
            type:Array,
            default:()=>[]
        },
        cur:{
            type:Number,
            default:-1
        }
    },
    methods:{
        hover(e){
            console.log(e,111)
        }
    }
}
</script>

<style scoped>
ul{
    list-style: none;
    margin:0px;
    padding:0px 20px;
    line-height: 32px;
    position: fixed;
    top:60px;
    bottom:50px;
    left:200px;
    right:50px;
    background:#fff;
    text-align: left;
    box-shadow: 0 2px 12px 0 rgba(0,0,0,.1);
    border-radius: 2px;
    z-index:11
}

ul li{
    display: inline-block;
    line-height: 20px;
    margin-right:20px;
    color:#909399
}
</style>

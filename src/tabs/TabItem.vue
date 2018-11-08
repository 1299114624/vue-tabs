<template>
<li class="tab" @click="tabAction" :class="{active:isActive}">
    <span :class="icon">❤</span>
    <span>{{name}}</span>
</li>
</template>

<script>
export default {
    name: 'tab-item',
    props:{
        name:String,
        icon:String,
    },
    data(){
        return{
            isActive : false
        }
    },
    methods:{
        tabAction(){
            this.$parent.handleTabAction(this.name);
            // console.log(this.$parent)
            this.isActive = true;
        }
    }
}
</script>

<style>
.tab{
    flex: 1;
    text-align: center;
    flex-direction: column;
    display: flex;
}
.tab span{
    flex: 1;
}
.tab span:first-of-type{
    font-size: 20px;
}
.tab .span:last-of-type{
    font-size: 12px;
}
.active{
    background-color: lightcoral;
}
</style>

<template>
<div id="app">

    <home v-if="selectIndex==0"/>
    <discover v-else-if="selectIndex==1"/>
    <hot v-else-if="selectIndex==2"/>
    <setting v-else-if="selectIndex==3"/>

    <!-- 四个页面：首页，热门，发现，设置 -->

    <tabs v-model="selectIndex">
        <tab-item name="首页" icon=""></tab-item>
        <tab-item name="热门" icon=""></tab-item>
        <tab-item name="发现" icon=""></tab-item>
        <tab-item name="设置" icon=""></tab-item>
    </tabs>

</div>
</template>

<script>
import discover from './pages/Discover'
import home from './pages/Home'
import hot from './pages/Hot'
import setting from './pages/Setting'

import Tabs from './tabs/Tabs'
import TabItem from './tabs/TabItem'
export default {
    components: {
        [Tabs.name]: Tabs,
        [TabItem.name]: TabItem,
        discover,
        home,
        hot,
        setting
    },
    data(){
        return {
            selectIndex: 1
        }
    }
}
</script>

<style>

</style>

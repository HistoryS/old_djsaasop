<template>
    <section class="app">
        <header class="this_header">
            <img src="./assets/img/djlogo.png" alt="logo">
            <h1>岱江saas运维平台</h1>
        </header>
        <section class="this_section">
            <nav class="this_nav">
                <el-menu :router="true" default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose">
                   <el-submenu index="1">
                        <template slot="title"><i class="el-icon-message"></i>放射设置</template>
                            <el-submenu index="1-1">
                                <template slot="title">系统设置</template>
                                <el-menu-item index="radiationPlugin">放射插件</el-menu-item>
                            </el-submenu>
                            <el-submenu index="1-2">
                                <template slot="title">模板设置</template>
                                <el-menu-item index="fastWrite">快速书写模板</el-menu-item>
                                <el-menu-item index="reportWrite">报告书写模板</el-menu-item>
                                <el-menu-item index="qualityScore">质控评分模板</el-menu-item>
                            </el-submenu>
                            <el-submenu index="1-3">
                                <template slot="title">其他设置</template>
                                <el-menu-item index="examineType">检查类型</el-menu-item>
                                <el-menu-item index="examineProject">检查项目</el-menu-item>
                                <el-menu-item index="examineArguments">检查参数</el-menu-item>
                                <el-menu-item index="diagnoseType">就诊类别</el-menu-item>
                                <el-menu-item index="shortcutCode">快捷代码</el-menu-item>
                                <el-menu-item index="contrastAgent">造影剂</el-menu-item>
                                <el-menu-item index="checkBody">检查部位</el-menu-item>
                            </el-submenu>
                    </el-submenu>
                    <el-submenu index="2">
                        <template slot="title"><i class="el-icon-setting"></i>系统设置</template>
                        <el-menu-item index="region">地区管理</el-menu-item>
                        <el-menu-item index="campus">院区管理</el-menu-item>
                        <el-menu-item index="role">角色管理</el-menu-item>
                        <el-menu-item index="user">用户管理</el-menu-item>
                        <el-menu-item index="dictionary">平台字典</el-menu-item>
                        <el-menu-item index="parameter">平台参数</el-menu-item>
                        <el-menu-item index="log">日志管理</el-menu-item>
                    </el-submenu>
                </el-menu>
            </nav>
            <router-view class="view router"></router-view>
        </section>
    </section>
</template>
<script>
export default {
    name: 'app',
    data() {
        return {
            activeIndex: '1',
            activeIndex2: '1',
        };
    },
    methods: {
        handleOpen(key, keyPath) {
            console.log(key, keyPath);
        },
        handleClose(key, keyPath) {
            console.log(key, keyPath);
        }
    }
}
</script>
<style lang="less" scoped>
    .app{
        display:flex;
        flex-direction:column;
        height: 100%;
        .this_header{
            height: 60px;
            display:flex;
            align-items:center;
            border-bottom:3px solid rgb(238, 246, 243);
            background:#009933;
            padding-left: .5em;
            img{
                height: 80%;
            }
            h1{
                margin-left: .5em;
                font-size: 22px;
                font-weight: 400;
                color: #fff;
            }
        }
        .this_section{
            height: 100%;
            width:100%;
            display:flex;
            // border:1px solid red;
            .this_nav{
                min-width: 200px;
                background: rgb(238, 246, 243);
                height: 100%;
                max-height: 100%;
                overflow: auto;
            }
            .view{
                display:flex;
                flex-direction:column;
                width:100%;
                height: 100%;
                flex-grow:2;
            }
        }
    }
</style>

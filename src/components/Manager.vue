<template>
    <div class="layout">
        <Row type="flex">
            <Col span="5" class="layout-menu-left">
                <Menu
                    active-name="1-1"
                    theme="dark"
                    width="auto"
                    :open-names="['1']"
                >
                    
                    <Submenu name="1">
                        <template slot="title">
                            <Icon type="ios-navigate"></Icon>
                            欢迎你，图书管理员:{{ msg }}
                        </template>
                        <MenuItem name="1-1" @click.native="interduce"
                            ><span>系统简介</span></MenuItem
                        >
                        <MenuItem name="1-2" @click.native="lookBook"
                            ><span>图书管理</span></MenuItem
                        >
                        <MenuItem name="1-3" @click.native="lookRecord"
                            ><span>借阅记录</span></MenuItem
                        >
                        <MenuItem name="1-4" @click.native="backLogin"
                            ><span>退出登录</span></MenuItem
                        >
                    </Submenu>
                </Menu>
            </Col>
            <Col span="19">
                <div class="layout-header"><h1 style="line-height:60px;">图书管理系统</h1></div>
                <div class="layout-breadcrumb">
                    <Breadcrumb>
                        <BreadcrumbItem href="#">{{ one_nav }}</BreadcrumbItem>
                        <BreadcrumbItem href="#">{{ two_nav }}</BreadcrumbItem>
                        <BreadcrumbItem>{{ three_nav }}</BreadcrumbItem>
                    </Breadcrumb>
                </div>
                <div class="layout-content">
                    <div class="layout-content-main">
                        <template id="bookManage"></template>
                        <template id="recordManage"></template>
                        <component :is="currentView"></component>
                    </div>
                </div>
                <div class="layout-copy">
                    2019-2020 &copy; 图书管理系统
                </div>
            </Col>
        </Row>
    </div>
</template>
<script>
import bookManage from "../components/BookManage.vue";
import recordManage from "../components/RecordManage.vue";
import interduce from "../components/interduce.vue";
import Button from "iview/src/components/button/button";
export default {
    name: "Manager",
    data() {
        return {
            msg: "haha",
            one_nav: "主页",
            two_nav: ">",
            three_nav: "系统简介",
            currentView: "interduce"
        };
    },
    mounted() {
        this.msg = window.localStorage.getItem("username");
    },
    methods: {
        backLogin(){
            window.location.href = 'http://localhost:8075';
        },
        lookBook() {
            this.one_nav = "主页";
            this.two_nav = "后台管理";
            this.three_nav = "图书管理";
            this.currentView = "bookManage";
        },
        lookRecord() {
            this.one_nav = "主页";
            this.two_nav = "后台管理";
            this.three_nav = "借阅记录";
            this.currentView = "recordManage";
        },
        interduce() {
            this.one_nav = "主页";
            this.two_nav = ">";
            this.three_nav = "系统简介";
            this.currentView = "interduce";
        }
    },
    components: {
        Button,
        bookManage: bookManage,
        recordManage: recordManage,
        interduce: interduce
    }
};
</script>
<style scoped>

.layout {
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    margin-top: -60px;
}
.layout-breadcrumb {
    padding: 10px 15px 0;
    text-align: left;
}
.layout-content {
    min-height: 200px;
    margin: 15px;
    overflow: hidden;
    background: #fff;
    border-radius: 4px;
}
.layout-content-main {
    padding: 10px;
}
.layout-copy {
    text-align: center;
    padding: 10px 0 20px;
    color: #9ea7b4;
}
.layout-menu-left {
    background: #464c5b;
}
.layout-header {
    height: 60px;
    background: #fff;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
}
.layout-logo-left {
    width: 90%;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    margin: 15px auto;
}
button {
    color: white;
}
</style>

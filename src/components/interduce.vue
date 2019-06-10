<template>
    <div class="container1">
        <h1 class="name">图书管理系统简介</h1>
        <h2 class="title">一、使用人群</h2>
        <ol class="content">
            <li class="li">图书管理员</li>
            <li class="li">老师</li>
            <li class="li">学生</li>
        </ol>
        <h2 class="title">二、关于登录注册</h2>
        <ol class="content">
            <li class="li">图书管理员请找系统维护人员进行注册</li>
            <li class="li">老师请找系统维护人员进行注册登录</li>
            <li class="li">学生请找图书系统管理员或者老师进行相关注册</li>
        </ol>
        <h2 class="title">三、如何操作</h2>
        <ol class="content">
            <li class="li">打开系统填入帐号密码验证码登录</li>
            <li class="li">不同身份的人员所看到的界面是不一样的</li>
            <li class="li">如有对当前身份的疑问请联系管理员</li>
        </ol>
        <h2 class="title">四、管理员拥有权限</h2>
        <ol class="content">
            <li class="li">添加删除修改用户</li>
            <li class="li">添加删除修改图书</li>
            <li class="li">借还图书操作</li>
            <li class="li">拥有一个超级管理员对用户身份的操作</li>
        </ol>
        <h2 class="title">五、其他注意事项</h2>
        <ol class="content">
            <li class="li">妥善保管好自己的帐号密码</li>
            <li class="li">如有忘记情况，及时联系管理员</li>
            <li class="li">对于系统还有其他好的建议或者反馈，联系管理员</li>
        </ol>
    </div>
</template>
<script type="es6">
export default {
    name: "Interduce",
};
</script>
<style scoped>

.title{
    text-align: left;
    margin-left: 20px;
    margin-bottom: 10px;
}
.li{
    text-align: left;
    font-size: 18px;
    
}
.content{
   margin-left: 60px; 
   margin-bottom: 10px;
}
</style>



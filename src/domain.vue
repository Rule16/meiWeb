<template>
    <!--new header start-->
    <!-- 头部区域开始 -->
    <div class="header">
        <!-- 内容主体区域 -->
        <div class="container">
            <!-- 上模块 -->
            <div class="top">
                <!-- 左模块 -->
                <div class="left">
                    <img src="./resource/img/logo.png" alt=""/>

                </div>
                <!-- 右模块 -->
                <div class="right clearfix">
                    <div class="search">
                        <input type="text" placeholder="请输入关键字" id="keyword"/>
                        <button onclick="search()">
                            <img src="./resource/img/search.png" alt=""/>
                        </button>
                    </div>






                    <div class="searchWord">
                        <ul class="clearfix">
                            <li>热搜词：</li>
                            <li  onclick="search_word('褐煤')">褐煤</li>
                            <li  onclick="search_word('竞价')">竞价</li>
                            <li  onclick="search_word('无烟煤')">无烟煤</li>
                        </ul>
                    </div>
                </div>
            </div>
            <!-- 下模块 -->
            <div class="bottom">
                <ul class="clearfix" id="topTab">
                    <li id="page-1" data-type="1" class="currentLi"><a href="javascript:;">首页</a><span class="nav_line"></span></li>

                    <li id="page-2" data-type="2"><a href="javascript:;">中长期合同</a><span class="nav_line"></span></li>


                    <li id="page-3" data-type="3"><a href="javascript:;" >现货交易</a><span class="nav_line"></span></li>

                    <li id="page-4" data-type="4"><a href="javascript:;">物流中心</a><span class="nav_line"></span></li>


                    <li id="page-5" data-type="5"><a href="javascript:;">质检中心</a><span class="nav_line"></span></li>

                    <li id="page-9" data-type="9"><a href="javascript:;">煤储管理</a><span class="nav_line"></span></li>

                    <li id="page-6" data-type="6"><a href="javascript:;">金融服务超市</a></li>

                </ul>
            </div>
        </div>

    </div>
    <!-- 头部区域结束 -->


    
    <div class="platform">
        <header>
            <div class="menu">
                <a href="#">首页</a>
                <a href="#">会员中心</a>
                <a href="#">2024年电煤中长期合同</a>
                <a href="#">2024年非电煤长期合同</a>
                <a href="#">2023年电煤中长期合同</a>
                <a href="#">2023年非电煤中长期合同</a>
                <a href="#">95306直通车</a>
                <a href="#">交收单</a>
                <a href="#">资金结算</a>
                <a href="#"></a>
            </div>
            <div class="login">
                <button @click="login">登录</button>
            </div>
        </header>

        <main>
            <aside>
                <ul>
                    <li>服务指引</li>
                    <li>待确认企业履约信息</li>
                    <li>已确认企业履约状态</li>
                    <li>中长期合同管理</li>
                    <li>中长期合同月度审核</li>
                    <li>中长期合同月度审核</li>
                    <li>中长期合同月度回款</li>
                    <li>月度调度合同回款</li>
                    <li>悬浮提示公示</li>
                </ul>
            </aside>

            <section>
                <h2>待确认企业履约信息</h2>
                <div class="search-filters">
                    <label>
                        <input type="radio" name="enterpriseType" value="public"> 公示型企业
                    </label>
                    <label>
                        <input type="radio" name="enterpriseType" value="traditional"> 传统煤炭企业
                    </label>
                    <label>
                        <input type="radio" name="enterpriseType" value="publicCoal"> 公示型企业与传统煤炭
                    </label>
                    <button @click="search">查询</button>
                </div>
                <table>
                    <thead>
                    <tr>
                        <th>操作</th>
                        <th>公示型企业</th>
                        <th>签订企业名称</th>
                        <th>煤种</th>
                        <th>签订数量（万吨）</th>
                        <th>平仓结算数量（万吨）</th>
                        <th>操作</th>
                    </tr>
                    </thead>
                    <tbody>
                    <tr>
                        <td>
                            <button @click="viewDetails">详情</button>
                        </td>
                        <td>安徽地方政府物资供应链有限公司</td>
                        <td>安徽地方政府物资供应链有限公司</td>
                        <td>褐煤</td>
                        <td>300</td>
                        <td>115</td>
                        <td>
                            <button @click="confirm">确认</button>
                        </td>
                    </tr>
                    </tbody>
                </table>
            </section>
        </main>
    </div>
</template>

<script>
    export default {
        name: 'CoalTradingPlatform',
        methods: {
            login() {
                alert('Login clicked');
            },
            search() {
                alert('Search clicked');
            },
            viewDetails() {
                alert('View Details clicked');
            },
            confirm() {
                alert('Confirm clicked');
            }
        }
    }
</script>

<style scoped>
    .platform {
        font-family: Arial, sans-serif;
    }

    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background: #f0f0f0;
        padding: 10px 20px;
    }

    .menu a {
        margin-right: 20px;
        text-decoration: none;
        color: #333;
    }

    .login button {
        padding: 5px 10px;
    }

    main {
        display: flex;
    }

    aside {
        width: 200px;
        background: #f8f8f8;
        padding: 20px;
    }

    aside ul {
        list-style-type: none;
        padding: 0;
    }

    aside li {
        margin-bottom: 10px;
    }

    section {
        flex: 1;
        padding: 20px;
    }

    .search-filters {
        display: flex;
        align-items: center;
        margin-bottom: 20px;
    }

    .search-filters label {
        margin-right: 10px;
    }

    table {
        width: 100%;
        border-collapse: collapse;
    }

    thead {
        background: #e8e8e8;
    }

    th, td {
        border: 1px solid #ccc;
        padding: 10px;
        text-align: left;
    }

    button {
        padding: 5px 10px;
    }

    body {
        height: 100%;
    }

    .container {
        width: 1200px;
        margin: auto;
    }

    /*right*/
    .contact-container {
        position: fixed;
        top: 45%;
        right: 0;
        bottom: 50%;
        z-index: 99;
        width: 94px;
        height: 320px;
        box-sizing: border-box;

    }
    .contact-container > ul {
        box-sizing: border-box;
        width: 100%;
        height: 100%;
        background: #265EC7;
        padding: 0 11px;
    }
    .contact-container > ul a{
        width: 100%;
        display: inline-block;
        text-align: center;
    }
    .contact-container > ul li h6{font-size: 12px;font-weight: normal;text-align: center;color: #FFFFFF}
    .contact-container > ul >li{
        height: 80px;
        /*padding: 26px 20px 20px 18px;*/
        padding: 15px 0px 15px 0px;
        border-bottom: 1px solid;
        border-color: rgba(236,237,239,0.42);
    }
    .contact-container > ul > li img {
        width: 34px;
        height: 34px;
    }
    .contact-container > ul > .gateway img,.contact-container > ul > .email img{width:40px}
    .contact-container > ul > .gateway a{
        padding-left: 2px;
    }

    /*头部*/
    .header {
        height: 158px;

    }

    .header .top .left {
        display: inline-block;
        width: 271px;
        height: 48px;
        margin-top: 31px;
        /*margin-left: 30px;*/
    }

    .header .top .left img {
        width: 100%;
        height: auto;
    }

    .header .top .right {
        float: right;
        /*width: 518px;*/
        margin-top: 29px;
    }

    .header .top .right .search {
        position: relative;
        width: 301px;
        height: 42px;
        overflow: hidden;
        /*box-shadow: 0 10px 20px 0 rgba(0, 0, 0, 0.10);*/
        background: #EEEFEF;
        border-radius: 30px;
    }

    .header .top .right .search input {
        padding: 12px 0 12px 18px;
        width: 100%;
        height: 100%;
        border: 0;

        opacity: 0.6;
        font-family: MicrosoftYaHei;
        font-size: 12px;
        color: #222222;
        letter-spacing: 0;
        line-height: 18px;
        font-weight: 400;
        background: #FFFFFF;
        border-radius: 30px;
        border: 1px solid #6BA2FF;
    }
    .header .top .right .search input:focus,.header .top .right .search input:hover{
        border: 1px solid #1B4CD9;
    }

    .header .top .right .search button {
        position: absolute;
        right: 0;
        top: 0;
        display: inline-block;
        width: 48px;
        height: 42px;
        border: 0;
        background: #6BA2FF;
    }

    .header .top .right .search button img {
        width: 15px;
        height: 15px;
        margin: auto;
    }

    .header .top .right .searchWord {
        width: 220px;
        margin: 8px 0 0 18px;
    }

    .header .top .right .searchWord li {
        float: left;
        margin-right: 8px;
        font-family: PingFangSC-Regular;
        font-size: 12px;
        color: #265EC7;
        letter-spacing: 0;
        line-height: 18px;
        font-weight: 400;
    }

    .header .bottom li {
        font-family: MicrosoftYaHei;
        height: 38px;
        float: left;
        position: relative;
        margin-right: 102px;
    }
    .header .bottom li:last-child{
        margin-right: 0px;

    }
    .header .bottom{
        margin: 37px 0 14px 0;
    }
    .header .bottom li a {
        display: block;
        height: 28px;
        /*line-height: 24px;*/
        font-family: MicrosoftYaHei;
        font-size: 20px;
        color: #666666;
        letter-spacing: 0;
        text-align: center;
        font-weight: 400;
    }
    .header .bottom li.nav_line{
        width: 1px;
        height: 18px;
        background: #979797;
        opacity: 0.34;
        margin: 5px 51px 0;
    }
    .header .bottom .currentLi::after{
        content: '';
        display: inline-block;
        width: 40px;
        height: 4px;
        background: #FE7904;
        border-radius: 1.5px;
        position: absolute;
        top: 30px;
        left: 50%;
        margin-left: -20px;
    }

    .header .bottom .currentLi a {
        font-family: PingFangSC-Semibold;
        font-size: 20px;
        color: #222222;
        letter-spacing: 0;
        text-align: center;
        font-weight: 600;
    }
    .header .bottom .nav_line{
        display: inline-block;
        width: 1px;
        height: 18px;
        background: #979797;
        opacity: 0.34;
        position: absolute;
        top: 5px;

    }
    .header .bottom #page-1 .nav_line{
        left: 91px;
    }
    .header .bottom #page-2 .nav_line{
        left: 151px;
    }
    .header .bottom #page-3 .nav_line,.header .bottom #page-4 .nav_line,.header .bottom #page-5 .nav_line,
    .header .bottom #page-7 .nav_line,.header .bottom #page-9 .nav_line{
        left: 131px;
    }
    /*工作台样式*/
    .header  .gzt{
        width: 121px;
        height: 35px;
        background-color: #FD8E1B;
        border-radius: 20px;
        position: relative;
        float: left;
        margin-left: 35px;
    }
    .header  .gzt .cl img{
        width: 33px;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
    }


    .header  .gzt .cl .clname{
        position: absolute;
        top: 50%;
        right: 13px;
        font-size: 13px;
        color: #FFFF;
        color: rgba(255,255,255,1);
        transform: translateY(-50%);
    }

</style>

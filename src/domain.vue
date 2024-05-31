<template>
    <div class="platform">
        <img id="img" src="./resouce/img/log.png" height="86" width="373"/>
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


</style>

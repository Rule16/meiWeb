<template>
    <div class="main">
        <div class="top w-full flex justify-center">
            <div class="content">
                <div class="top-content">
                    <img src="./resource/img/logo.png"/>
                    <div class="flex">
                        <div class="company-info">
                            <div class="company-name">安徽电力股份有限公司淮南田家庵发电分公司</div>
                            <div class="member">未缴费中长期会员</div>
                        </div>
                        <div class="log-out">退出</div>
                    </div>
                </div>
                <div class="top-menu">
                    <div
                            class="menu-item"
                            :class="{'active-menu-item': idx == activeMenu}"
                            v-for="(item, idx) in menuList"
                            :key="idx"
                            @click="checkMenu(idx)"
                    >
                        {{item}}
                        <div class="menu-line" :style="{visibility: idx == activeMenu ? 'visible' : 'hidden'}"></div>
                    </div>
                </div>
            </div>
        </div>

        <div class="flex w-full justify-center main-content">
            <div class="sign-info">
                <div class="left-menu">
                    <div
                            class="left-menu-item"
                            v-for="(item, idx) in leftMenuList"
                            :key="idx"
                            :class="{'left-menu-item-active': idx == activeLeftMenu}"
                            @click="checkLeftMenu(idx)"
                    >{{item}}
                    </div>
                </div>
                <div class="right-info">
                    <div class="right-top">
                        <div class="right-check-menu">我的工作台 / {{leftMenuList[activeLeftMenu]}}</div>
                        <div class="right-top-time">开市时间：00:00 - 24:00</div>
                    </div>
                    <div class="right-content">
                        <div class="company-tabs">
                            <div class="tabs-item"
                                 v-for="(item, idx) in companyTabs"
                                 :key="idx"
                                 :class="{'active-tab': idx == activeTab}"
                                 @click="checkTab(idx)"
                            >{{item}}
                            </div>
                        </div>
                        <div class="table-info">
                            <div class="table-form flex justify-between">
                                <div>
                                    <el-input v-model="keyword1" class="table-input"></el-input>
                                    <el-input v-model="keyword2" class="table-input"></el-input>
                                    <el-input v-model="keyword3" class="table-input"></el-input>
                                </div>
                                <div>
                                    <el-button style="padding: 10px 40px;" color="#626aef" round>查询</el-button>
                                    <el-button type="text" style="color: #6478D3">重置</el-button>
                                </div>
                            </div>
                            <el-table class="table-data" :data="tableData">
                                <el-table-column align="center" label="操作" width="100">
                                    <template #default>
                                        <el-button class="secure-about" color="#6478D3" round plain>解除关联</el-button>
                                    </template>
                                </el-table-column>
                                <el-table-column align="center" prop="companyName" label="公示用煤企业" width="310"></el-table-column>
                                <el-table-column align="center" prop="aboutCompanyName" label="关联企业名称" width="310"></el-table-column>
                                <el-table-column align="center" prop="status" label="审核状态" width="100"></el-table-column>
                                <el-table-column align="center" prop="number" label="需求量（万吨）" width="130"></el-table-column>
                                <el-table-column align="center" prop="auditNumber" label="平台核验通过量（万吨）" width="180"></el-table-column>
                            </el-table>
                            <div class="flex justify-between" style="margin-top: 15px">
                                <el-button class="secure-about" color="#6478D3" round plain>新增关联</el-button>
                                <div style="color: #999999">显示第 1 到第 0 条记录，总共 0 条记录 </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'CoalTradingPlatform',
        data() {
            return {
                menuList: [
                    "首页", "会员中心", "2024年电煤中长期合同", "2024年非电煤中长期合同", "2023年电煤中长期合同", "2023年非电煤中长期合同", "95306直通车", "交收单", "奖金结算",
                ],
                activeMenu: 2,
                leftMenuList: [
                    "服务指引", "供需企业信息公示", "关联公示签约信息", "已关联公示信息授权", "中长期合同录入", "中长期合同确认", "中长期合同查询", "中长期合同签订", "月度履约数据报送", "履约情况公示"
                ],
                activeLeftMenu: 2,
                companyTabs: ['煤炭企业', '用煤企业'],
                activeTab: 1,
                tableData: [
                    {
                        companyName: '安徽电力股份有限公司淮南田家庵发电分公司',
                        aboutCompanyName: '安徽电力股份有限公司淮南田家庵发电分公司',
                        status: '审核通过',
                        number: '300',
                        auditNumber: '115',
                    }
                ],
                keyword1: '公示用煤企业',
                keyword2: '审核状态(全部)',
                keyword3: '公示用煤企业营业执照名称',
            }
        },
        methods: {
            checkMenu(idx) {
                this.activeMenu = idx
            },
            checkLeftMenu(idx) {
                this.activeLeftMenu = idx
            },
            checkTab(idx) {
                this.activeTab = idx
            },
        }
    }
</script>

<style scoped>
    .main {
        width: 100%;
        height: 100vh;
        background: url("./resource/img/main_bg.png") no-repeat fixed;
        font-size: 14px;
        display: flex;
        flex-direction: column;
    }

    .top {
        box-shadow: 1px 1px 20px 0px #E7E5E5;
    }

    .company-info {
        margin-right: 25px;
    }

    .member {
        margin-top: 5px;
    }

    .log-out {
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.25);
        border-radius: 20px;
        padding: 10px 40px;
        color: #F08D1D;
        height: fit-content;
        cursor: pointer;
    }

    .content {
        width: 65%;
    }

    .main-content {
        flex: 1;
        margin: 30px 0;
    }

    .top-content {
        display: flex;
        justify-content: space-between;
        margin: 20px 0;
    }

    .top-menu {
        display: flex;
        align-items: center;
    }

    .menu-item {
        margin-right: 25px;
        cursor: pointer;
        font-family: MicrosoftYaHei-Bold;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .menu-item:hover .menu-line {
        visibility: visible !important;
    }

    .menu-line {
        height: 2px;
        background: #FF8A48;
        width: 50%;
        margin-top: 5px;
        visibility: hidden;
    }

    .active-menu-item {
        font-weight: bold;
    }

    .sign-info {
        width: 65%;
        display: flex;
    }

    .left-menu {
        width: 190px;
        background: rgba(122, 174, 242, 0.6);
        margin-right: 10px;
    }

    .right-info {
        width: calc(100% - 190px - 30px);
    }

    .right-top {
        display: flex;
        justify-content: space-between;
        align-items: center;
        color: #6478D3;
        padding-left: 25px;
    }

    .right-top-time {
        border: 1px solid #6478D3;
        border-radius: 14px;
        padding: 5px 20px;
    }

    .left-menu-item {
        padding: 15px;
        padding-left: 30px;
        cursor: pointer;
    }

    .left-menu-item-active {
        background-color: #6478D3;
        border-left: 4px solid #F08D1D;
        color: #ffffff;
    }

    .right-content {
        border: 1px solid #efefef;
        margin-top: 30px;
        height: calc(100% - 33px - 30px)
    }

    .company-tabs {
        display: flex;
        width: 100%;
        background: #fbfbfb;
        border-bottom: 1px solid #efefef;
    }

    .tabs-item {
        padding: 7px 15px;
        cursor: pointer;
    }

    .active-tab {
        background: #6478D3;
        color: #ffffff;
    }

    .table-info {
        padding: 0 25px;
        padding-top: 60px;
    }


    .table-data {
        width: 100%;
        margin-top: 20px;
        box-shadow: -1px 0px 10px 0px #c3c1c1;
    }

    .secure-about {

    }

    .table-input {
        width: 200px;
        margin-right: 20px;

    }

    /deep/ .table-input .el-input__wrapper {
        border-radius: 15px;
    }

    /deep/ .el-table th.el-table__cell {
        background: #6478D3;
        color: #ffffff;
        padding: 15px 0;
    }

    /deep/ .el-table__body-wrapper .el-scrollbar__bar {
        display: block !important;
    }

    /deep/ .el-scrollbar__thumb {
        background: #6478D3;
        opacity: 1;
    }

    /deep/ .el-table--enable-row-transition .el-table__body td.el-table__cell {
        padding: 15px 0;
    }

</style>

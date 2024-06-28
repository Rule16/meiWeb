<template>
    <div class="main">
        <div class="top w-full flex justify-center">
            <div class="content">
                <div class="top-content">
                    <img src="./resource/img/logo.png"/>
                    <div class="flex">
                        <div class="company-info">
                            <div class="company-name">国家能源集团宝庆发电有限公司</div>
                            <div class="member">&emsp;中长期公员&emsp;<span class="expire-time">截至2024年12月31日</span></div>
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
                        <!-- 供需企业信息公示-->
                        <xinXiGongShi v-if="activeLeftMenu == 1"/>

                        <!-- 关联公示签约信息-->
                        <qianYueXinxi v-if="activeLeftMenu == 2"/>

                        <!-- 中长期合同查询-->
                        <heTongChaXun v-if="activeLeftMenu == 6"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

    import qianYueXinxi from './components/qianYueXinXi.vue'
    import xinXiGongShi from './components/xinXiGongShi.vue'
    import heTongChaXun from './components/heTongChaXun.vue'

    export default {
        name: 'CoalTradingPlatform',
        components: {qianYueXinxi, xinXiGongShi, heTongChaXun},
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
            }
        },
        methods: {
            checkMenu(idx) {
                this.activeMenu = idx
            },
            checkLeftMenu(idx) {
                this.activeLeftMenu = idx
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

    .company-name {
        font-size: 16px;
    }

    .member {
        margin-top: 5px;
        font-size: 12px;
    }

    .expire-time {
        color: #9b9696;
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
</style>

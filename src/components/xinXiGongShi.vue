<template>
    <!-- 供需企业信息公示-->
    <div class="gongShi">
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
                        <el-button @click="showInfo" class="secure-about" color="#6478D3" round plain>公示详情</el-button>
                    </template>
                </el-table-column>
                <el-table-column align="center" prop="companyName" label="公示用煤企业" width="310"></el-table-column>
                <el-table-column align="center" prop="aboutCompanyName" label="关联企业名称" width="310"></el-table-column>
                <el-table-column align="center" prop="status" label="审核状态" width="100"></el-table-column>
                <el-table-column align="center" prop="number" label="需求量（万吨）" width="130"></el-table-column>
                <el-table-column align="center" prop="auditNumber" label="平台核验通过量（万吨）" width="180"></el-table-column>
            </el-table>
            <div class="flex justify-between" style="margin-top: 15px">
                <div></div>
                <div style="color: #999999">显示第 1 到第 0 条记录，总共 0 条记录</div>
            </div>
        </div>

        <el-dialog
                v-model="infoDialog"
                title="详情"
                width="930px">
            <div class="info-content">
                <div class="info-title">企业公示</div>
                <div class="info-container">
                    <div class="info-item">公示用煤名称：华电莱州发电有限公司</div>
                    <div class="info-item">企业名称：华电莱州发电有限公司</div>
                    <div class="info-item">关联企业名称：华电莱州发电有限公司</div>
                    <div class="flex" style="margin: 30px 0">
                        <div style="width: 400px">所属省：山东</div>
                        <div>所属市：莱州</div>
                    </div>
                    <div class="flex" style="margin: 30px 0">
                        <div style="width: 400px">联系人：孔凡平</div>
                        <div>联系电话：</div>
                    </div>
                </div>
                <div class="info-title" style="margin-top: 20px">签约信息</div>
                <div class="info-container">
                    <div class="flex" style="margin: 30px 0">
                        <div style="width: 400px">平台核验通过量：215&emsp;万吨</div>
                        <div>需求量：575&emsp;万吨</div>
                    </div>
                    <div class="flex" style="margin: 30px 0">
                        <div style="width: 400px">确认量：215&emsp;万吨</div>
                        <div>纳入电煤台账量：215&emsp;万吨</div>
                    </div>
                </div>
                <div class="flex justify-center" style="margin-top: 40px">
                    <el-button style="padding: 10px 40px;" color="#626aef" round @click="infoDialog = false">关闭</el-button>
                </div>
            </div>
        </el-dialog>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                keyword1: '公示用煤企业',
                keyword2: '审核状态(全部)',
                keyword3: '公示用煤企业营业执照名称',
                companyTabs: ['煤炭企业', '用煤企业', '第三方企业'],
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
                infoDialog: false,
            }
        },
        methods: {
            checkTab(idx) {
                this.activeTab = idx
            },
            showInfo() {
                this.infoDialog = true
            },
        },
    }
</script>
<style scoped>
    .gongShi {
        width: 100%;
        height: 100%;
        position: relative;
    }
    .info-content {
        padding: 20px 50px;
    }

    .info-title {
        font-size: 16px;
    }

    .info-container {
        border: 1px solid;
        border-radius: 15px;
        padding: 0px 40px;
        margin: 5px 10px;
    }

    .info-item {
        width: 400px;
        margin: 30px 0;
    }

    /deep/ .el-overlay {
        position: absolute;
        width: 100%;
        height: 100%;
    }

    /deep/ .el-overlay-dialog {
        left: 160px;
        bottom: -19px;
        top: auto;
    }

    /deep/ .el-dialog {
        padding: 0px
    }

    /deep/ .el-dialog__header {
        padding: 7px 0px;
        background: #efefef;
        text-align: center;
    }

    /deep/ .el-dialog__close {
        display: none;
    }

    /deep/ .el-dialog__title {
        font-size: 14px
    }
</style>
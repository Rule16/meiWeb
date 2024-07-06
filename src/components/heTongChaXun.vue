<template>
    <!-- 中长期合同查询-->
    <div class="height: 100%; overflow: auto">
        <div class="table-info" style="padding-top: 0px">
            <div class="table-form flex justify-between" style="align-items: flex-end">
                <div>
                    <el-input v-model="keyword1" class="table-input"></el-input>
                    <el-input v-model="keyword2" class="table-input"></el-input>
                    <el-input v-model="keyword3" class="table-input"></el-input>
                    <el-input v-model="keyword4" class="table-input"></el-input>
                    <el-input v-model="keyword5" class="table-input"></el-input>
                    <el-input v-model="keyword6" class="table-input"></el-input>
                    <el-input v-model="keyword7" class="table-input"></el-input>
                </div>
                <div style="width: 700px">
                    <el-button style="padding: 10px 30px;" color="#626aef" round>查询</el-button>
                    <el-button type="text" style="color: #6478D3">重置</el-button>
                    <el-button style="padding: 10px 30px;" color="#626aef" round>导出excel</el-button>
                </div>
            </div>
            <div class="flex justify-center">
                <div class="title">中长期合同查询</div>
            </div>
            <el-table class="table-data" :data="tableData">
                <el-table-column align="center" prop="number" label="合同编号" width="140"></el-table-column>
                <el-table-column align="center" prop="seller" label="出卖人" width="260"></el-table-column>
                <el-table-column align="center" prop="buyer" label="买受人" width="200"></el-table-column>
                <el-table-column align="center" prop="auditStatus" label="合同流程状态" width="200">
                    <template #default="{row}">
                        <span v-if="row.auditStatus == 1">平台核验通过</span>
                        <div v-else class="flex justify-center" style="align-items: center">
                            <span>需方审核不通过</span>
                            <el-button class="secure-about" color="#6478D3" round plain style="margin-left: 5px">查看原因</el-button>
                        </div>
                    </template>
                </el-table-column>
                <el-table-column align="center" prop="auditRules" label="审核规范" width="205">
                    <template #default="{row}">
                        <span v-if="row.auditRules == 1">规范</span>
                        <el-button v-if="row.auditRules == 2" class="secure-about" color="#6478D3" round plain>规范(待上传经济合同)</el-button>
                        <el-button v-if="row.auditRules == 3" class="secure-about" color="#6478D3" round plain>不规范</el-button>
                    </template>
                </el-table-column>
                <el-table-column align="center" prop="contractNum" label="合同数量"></el-table-column>
                <el-table-column align="center" prop="transportType" label="运输方式"></el-table-column>
            </el-table>
            <div class="flex items-center" style="margin-top: 60px">
                <div class="other-item">合同预览</div>
                <div class="other-item">承诺书下载</div>
                <div class="other-item">规范调整</div>
                <div class="other-item">运输信息</div>
                <div class="other-item">运力申请</div>
                <div class="other-item">查看运力</div>
                <div class="other-item">运力合同下载</div>
                <div class="other-item">修改合同条款</div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                keyword1: '合同编号',
                keyword2: '出卖人',
                keyword3: '云南能投曲靖发电有限公司',
                keyword4: '是否台账（全部）',
                keyword5: '是否废弃（否）',
                keyword6: '审核规范（全部）',
                keyword7: '运输方式（全部）',
                companyTabs: ['煤炭企业', '用煤企业'],
                activeTab: 1,
                tableData: [
                    {
                        number: '2024CXY102332',
                        seller: '贵州众一全彩影煤炭销售有限公司',
                        buyer: '云南能投曲靖发电有限公司',
                        auditStatus: 1,
                        auditRules: 1,
                        contractNum: '60.00',
                        transportType: '铁路直达',
                    },{
                        number: '2024CXYA00659',
                        seller: '山煤国际能原集团股份有限公司',
                        buyer: '云南能投曲靖发电有限公司',
                        auditStatus: 1,
                        auditRules: 2,
                        contractNum: '30.00',
                        transportType: '铁路直达',
                    },{
                        number: '2024CXYA00621',
                        seller: '山西成功煤炭经销有限公司',
                        buyer: '云南能投曲靖发电有限公司',
                        auditStatus: 1,
                        auditRules: 2,
                        contractNum: '5.0',
                        transportType: '铁路直达',
                    },
                ],
            }
        },
        methods: {
            checkTab(idx) {
                this.activeTab = idx
            },
        }
    }
</script>
<style scoped>
.title {
    font-size: 16px;
    font-weight: bold;
    font-family: MicrosoftYaHei-Bold;
    color: #ff8300;
    border-top: 2px solid #ff8300;
    border-bottom: 2px solid #ff8300;
    padding: 5px 10px;
    width: fit-content;
    margin: 50px 0 15px;
}

    .other-item {
        color: #000997;
        border: 1px solid #000997;
        border-radius: 6px;
        padding: 1px 5px;
        margin: 0 5px;
        font-size: 12px;
    }
</style>
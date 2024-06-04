<template>
    <!-- 关联公示签约信息-->
    <div>
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
</template>
<script>
    export default {
        data() {
            return {
                keyword1: '公示用煤企业',
                keyword2: '审核状态(全部)',
                keyword3: '公示用煤企业营业执照名称',
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

</style>
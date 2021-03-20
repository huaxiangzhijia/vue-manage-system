<template>
    <div>
        <div class="crumbs">
            <el-breadcrumb separator="/">
                <el-breadcrumb-item>
                    <i class="el-icon-pie-chart"></i> schart图表
                </el-breadcrumb-item>
            </el-breadcrumb>
        </div>
        <div class="container">
            <div class="plugins-tips">
                vue-schart：vue.js封装sChart.js的图表组件。
                访问地址：
                <a
                    href="https://github.com/lin-xin/vue-schart"
                    target="_blank"
                >vue-schart</a>
            </div>
            <div class="schart-box">
                <div class="content-title">柱状图</div>
                <schart class="schart" canvasId="bar" :options="options1"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">折线图</div>
                <schart class="schart" canvasId="line" :options="options2"></schart>
            </div>
            <div class="schart-box">
                <div class="content-title">饼状图</div>
                <schart class="schart" canvasId="pie" :options="options3"></schart>
            </div>
            
        </div>
    </div>
</template>

<script>
import Schart from 'vue-schart';
export default {
    name: 'basecharts',
    components: {
        Schart
    },
    data() {
        return {
            options1: {
                type: 'bar',
                title: {
                    text: '成绩'
                },
                bgColor: '#fbfbfb',
                labels: ['第一次月考', '第二次月考', '期中考试', '第三次', '期末考试'],
                datasets: [
                    {
                        label: '语文',
                        fillColor: 'rgba(241, 49, 74, 0.5)',
                        data: [100, 110, 90, 120, 111]
                    },
                    {
                        label: '数学',
                        data: [100, 89, 92, 135, 120]
                    },
                    {
                        label: '英语',
                        data: [114, 98, 98, 95, 100]
                    }
                ]
            },
            options2: {
                type: 'line',
                title: {
                    text: '成绩趋势'
                },
                bgColor: '#fbfbfb',
                labels: ['第一次月考', '第二次月考', '期中考试', '第三次月考', '期末考试'],
                datasets: [
                    {
                        label: '语文',
                        data: [100, 110, 90, 120, 111]
                    },
                    {
                        label: '数学',
                        data: [100, 89, 92, 135, 120]
                    },
                    {
                        label: '英语',
                        data: [114, 98, 98, 95, 100]
                    }
                ]
            },
            options3: {
                type: 'pie',
                title: {
                    text: '服装品类销售饼状图'
                },
                legend: {
                    position: 'left'
                },
                bgColor: '#fbfbfb',
                labels: ['语文', '数学', '英语'],
                datasets: [
                    {
                        data: [110, 120, 90]
                    }
                ]
            },
            
        };
    }
};
</script>

<style scoped>
.schart-box {
    display: inline-block;
    margin: 20px;
}
.schart {
    width: 600px;
    height: 400px;
}
.content-title {
    clear: both;
    font-weight: 400;
    line-height: 50px;
    margin: 10px 0;
    font-size: 22px;
    color: #1f2f3d;
}
</style>
<template>
    <div class="flex">
        <div class="left">
            <div class="title">BMS Overview</div>
            <div class="leftMain">
                <div class="battery">
                    <img src="../../assets/img/icon-battery.png" alt="" />
                    <el-progress
                        :text-inside="true"
                        :stroke-width="92"
                        :percentage="70"
                        status="success"
                    ></el-progress>
                </div>
                <div class="time">1h : 02min</div>
                <div class="card">
                    <div class="item">
                        <div class="name">Temp</div>
                        <div class="txt">18C</div>
                    </div>
                    <div class="item">
                        <div class="name">Current</div>
                        <div class="txt">1.3A</div>
                    </div>
                    <div class="item">
                        <div class="name">Voltage</div>
                        <div class="txt">21.7V</div>
                    </div>
                </div>
                <div class="change">
                    <el-switch
                        v-model="changeMOS"
                        active-color="#6672fb"
                        inactive-text="Discharge MOS"
                        active-text="Charge"
                    >
                    </el-switch>
                </div>
                <el-button type="primary"
                    >View Details<i
                        class="el-icon-right"
                        style="margin-left: 8px"
                    ></i
                ></el-button>
            </div>
        </div>
        <div class="right">
            <div class="title">Cells</div>
            <div id="chart"></div>
        </div>
    </div>
</template>
<script>
import * as echarts from "echarts";
export default {
    data() {
        return {
            changeMOS: false,
        };
    },
    components: {},
    created() {},
    mounted() {
        this.initMap();
    },
    methods: {
        initMap() {
            let myChart = echarts.init(document.getElementById("chart"));
            // prettier-ignore
            let dataAxis = ['点', '击', '柱', '子', '或', '者', '两', '指', '在', '触', '屏', '上', '滑', '动', '能', '够', '自', '动', '缩', '放'];
            // prettier-ignore
            let data = [220, 182, 191, 234, 290, 330, 310, 123, 442, 321, 90, 149, 210, 122, 133, 334, 198, 123, 125, 220];
            let yMax = 500;
            let dataShadow = [];
            for (let i = 0; i < data.length; i++) {
                dataShadow.push(yMax);
            }
            myChart.setOption({
                xAxis: {
                      show: false,
                    type: "value",
                    axisLabel: {
                        inside: true,
                        color: "#fff",
                    },
                    axisTick: {
                        show: false,
                    },
                    axisLine: {
                        show: false,
                    },
                    z: 10,
                },
                yAxis: {
                    type: "category",
                    axisTick: {
                        show: false,
                    },
                    axisLine: {
                        show: false,
                    },
                    data: [
                        "1",
                        "2",
                        "3",
                        "4",
                        "5",
                        "6",
                        "7",
                        "8",
                        "9",
                        "10",
                        "11",
                        "12",
                    ],
                },
                series: [
                    {
                        data: [
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(255,112,112,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(255,112,112,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(92,123,217,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(92,123,217,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(255,136,224,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(255,136,224,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(169,105,198,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(169,105,198,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(255,145,90,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(255,145,90,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(64,178,125,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(64,178,125,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(126,211,244,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(126,211,244,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(250,200,88,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(250,200,88,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(145,204,117,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(145,204,117,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(24,141,240,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(24,141,240,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 10,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(89,225,164,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(89,225,164,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                            {
                                value: 20,
                                itemStyle: {
                                    color: new echarts.graphic.LinearGradient(
                                        0,
                                        0,
                                        1,
                                        0,
                                        [
                                            {
                                                offset: 0.8,
                                                color: "rgba(102,205,221,0.5)",
                                            },
                                            {
                                                offset: 0,
                                                color: "rgba(102,205,221,1)",
                                            },
                                        ]
                                    ),
                                },
                            },
                        ],
                        type: "bar",
                    },
                ],
            });
            let that = this;
            // myChart.on('click', function (params) {
            //     that.$emit('openGridManage', params.name)
            // })
            myChart.getZr().on("click", (params) => {
                let pointInPixel = [params.offsetX, params.offsetY];
                if (myChart.containPixel("grid", pointInPixel)) {
                    let xIndex = myChart.convertFromPixel({ seriesIndex: 0 }, [
                        params.offsetX,
                        params.offsetY,
                    ])[0];
                    that.$emit("openGridManage", that.xAxisList[xIndex]);
                }
            });
        },
    },
};
</script>
<style lang="less" scoped>
#chart {
    width: 100%;
    height: calc(100% - 100px);
}
.left {
    width: 50%;
    border-right: 1px solid #f1f1f1;
    .leftMain {
        height: calc(100% - 180px);
        .battery {
            position: relative;
            width: 200px;
            height: 100px;
            margin: 80px auto 50px;
            img {
                display: block;
                width: 100%;
            }
            .el-progress {
                position: absolute;
                top: 8px;
                left: 96px;
                transform: translate(-50%, 0);
                width: 175px;
            }
            /deep/ .el-progress-bar__outer {
                border-radius: 8px;
            }
            /deep/ .el-progress-bar__inner {
                border-radius: 8px;
                background-color: #6672fb;
                // background: linear-gradient(to right, #333, #fff);
                .el-progress-bar__innerText {
                    font-size: 26px;
                    font-weight: 600;
                    // color: #333;
                }
            }
        }
        .time {
            font-size: 18px;
            font-weight: 600;
            letter-spacing: 0.6px;
        }
        .card {
            display: flex;
            align-items: center;
            justify-content: space-around;
            margin-top: 50px;
            .item {
                width: 120px;
                height: 90px;
                background: #6672fb;
                border-radius: 8px;
                text-align: center;
                color: #fff;
                display: flex;
                align-items: center;
                justify-content: space-around;
                flex-direction: column;
                .name {
                    font-size: 15px;
                    font-weight: 400;
                }
                .txt {
                    font-size: 18px;
                    font-weight: 600;
                }
            }
        }
        .change {
            margin-top: 100px;
            /deep/ .el-switch {
                .el-switch__label {
                    span {
                        font-size: 16px;
                        font-weight: 500;
                    }
                    &.is-active {
                        color: #6672fb;
                        span {
                            font-weight: 600;
                        }
                    }
                }
            }
        }
        .el-button--primary {
            background-color: #6672fb;
            border-color: #6672fb;
            margin-top: 100px;
        }
    }
}
.right {
    width: 50%;
}
.flex {
    height: 100%;
}
.title {
    font-size: 30px;
    font-weight: 600;
    height: 100px;
    display: flex;
    align-items: flex-end;
    justify-content: center;
}
</style>

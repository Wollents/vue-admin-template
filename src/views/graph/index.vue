<template>
    <div id="graph-panel" style="width:100%;height:calc(100vh - 16px);background-color:#efefef;"></div>
</template>


<script>
import VisGraph from '@/assets/js/visgraph.min.js'
import LayoutFactory from '@/assets/js/visgraph-layout.min.js'
export default {
    components: {
        VisGraph,
        LayoutFactory
    },
    data() {
        return {
            visGraph: null,
            layout: null,
            graphData: {
                "nodes": [
                    {
                        "id": 1,
                        "label": 1,
                        "x": 713,
                        "y": 36,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 2,
                        "label": 2,
                        "x": 632,
                        "y": 174,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 3,
                        "label": 3,
                        "x": 511,
                        "y": 75,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 4,
                        "label": 4,
                        "x": 668,
                        "y": 279,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 5,
                        "label": 5,
                        "x": 976,
                        "y": 68,
                        "width": 58,
                        "color": "rgb(38,152,121)"
                    },
                    {
                        "id": 6,
                        "label": 6,
                        "x": 868,
                        "y": -198,
                        "width": 58,
                        "color": "rgb(38,152,121)"
                    },
                    {
                        "id": 7,
                        "label": 7,
                        "x": 976,
                        "y": -102,
                        "width": 58,
                        "color": "rgb(38,152,121)"
                    },
                    {
                        "id": 8,
                        "label": 8,
                        "x": 556,
                        "y": 287,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 9,
                        "label": 9,
                        "x": 451,
                        "y": -27,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 10,
                        "label": 10,
                        "x": 285,
                        "y": 147,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 11,
                        "label": 11,
                        "x": 897,
                        "y": -47,
                        "width": 58,
                        "color": "rgb(38,152,121)"
                    },
                    {
                        "id": 12,
                        "label": 12,
                        "x": 755,
                        "y": -193,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 13,
                        "label": 13,
                        "x": 866,
                        "y": 256,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 14,
                        "label": 14,
                        "x": 473,
                        "y": 169,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 15,
                        "label": 15,
                        "x": 44,
                        "y": -47,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 16,
                        "label": 16,
                        "x": 56,
                        "y": -122,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 17,
                        "label": 17,
                        "x": 1025,
                        "y": -314,
                        "width": 58,
                        "color": "rgb(38,152,121)"
                    },
                    {
                        "id": 18,
                        "label": 18,
                        "x": 778,
                        "y": 283,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 19,
                        "label": 19,
                        "x": 155,
                        "y": 141,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 20,
                        "label": 20,
                        "x": 546,
                        "y": -38,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 21,
                        "label": 21,
                        "x": 93,
                        "y": 89,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 22,
                        "label": 22,
                        "x": 847,
                        "y": 161,
                        "width": 58,
                        "color": "rgb(83,186,23)"
                    },
                    {
                        "id": 23,
                        "label": 23,
                        "x": 53,
                        "y": 24,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 24,
                        "label": 24,
                        "x": 225,
                        "y": -281,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 25,
                        "label": 25,
                        "x": 505,
                        "y": -428,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 26,
                        "label": 26,
                        "x": 353,
                        "y": -437,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 27,
                        "label": 27,
                        "x": 70,
                        "y": -324,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 28,
                        "label": 28,
                        "x": 401,
                        "y": -234,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 29,
                        "label": 29,
                        "x": 404,
                        "y": -96,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 30,
                        "label": 30,
                        "x": 99,
                        "y": -194,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 31,
                        "label": 31,
                        "x": 374,
                        "y": 119,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 32,
                        "label": 32,
                        "x": 485,
                        "y": -190,
                        "width": 58,
                        "color": "rgb(81,40,254)"
                    },
                    {
                        "id": 33,
                        "label": 33,
                        "x": 257,
                        "y": -11,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    },
                    {
                        "id": 34,
                        "label": 34,
                        "x": 263,
                        "y": -111,
                        "width": 58,
                        "color": "rgb(234,28,219)"
                    }
                ],
                "links": [
                    {
                        "source": 2,
                        "target": 1
                    },
                    {
                        "source": 3,
                        "target": 1
                    },
                    {
                        "source": 3,
                        "target": 2
                    },
                    {
                        "source": 4,
                        "target": 1
                    },
                    {
                        "source": 4,
                        "target": 2
                    },
                    {
                        "source": 4,
                        "target": 3
                    },
                    {
                        "source": 5,
                        "target": 1
                    },
                    {
                        "source": 6,
                        "target": 1
                    },
                    {
                        "source": 7,
                        "target": 1
                    },
                    {
                        "source": 7,
                        "target": 5
                    },
                    {
                        "source": 7,
                        "target": 6
                    },
                    {
                        "source": 8,
                        "target": 1
                    },
                    {
                        "source": 8,
                        "target": 2
                    },
                    {
                        "source": 8,
                        "target": 3
                    },
                    {
                        "source": 8,
                        "target": 4
                    },
                    {
                        "source": 9,
                        "target": 1
                    },
                    {
                        "source": 9,
                        "target": 3
                    },
                    {
                        "source": 10,
                        "target": 3
                    },
                    {
                        "source": 11,
                        "target": 1
                    },
                    {
                        "source": 11,
                        "target": 5
                    },
                    {
                        "source": 11,
                        "target": 6
                    },
                    {
                        "source": 12,
                        "target": 1
                    },
                    {
                        "source": 13,
                        "target": 1
                    },
                    {
                        "source": 13,
                        "target": 4
                    },
                    {
                        "source": 14,
                        "target": 1
                    },
                    {
                        "source": 14,
                        "target": 2
                    },
                    {
                        "source": 14,
                        "target": 3
                    },
                    {
                        "source": 14,
                        "target": 4
                    },
                    {
                        "source": 17,
                        "target": 6
                    },
                    {
                        "source": 17,
                        "target": 7
                    },
                    {
                        "source": 18,
                        "target": 1
                    },
                    {
                        "source": 18,
                        "target": 2
                    },
                    {
                        "source": 20,
                        "target": 1
                    },
                    {
                        "source": 20,
                        "target": 2
                    },
                    {
                        "source": 22,
                        "target": 1
                    },
                    {
                        "source": 22,
                        "target": 2
                    },
                    {
                        "source": 26,
                        "target": 24
                    },
                    {
                        "source": 26,
                        "target": 25
                    },
                    {
                        "source": 28,
                        "target": 3
                    },
                    {
                        "source": 28,
                        "target": 24
                    },
                    {
                        "source": 28,
                        "target": 25
                    },
                    {
                        "source": 29,
                        "target": 3
                    },
                    {
                        "source": 30,
                        "target": 24
                    },
                    {
                        "source": 30,
                        "target": 27
                    },
                    {
                        "source": 31,
                        "target": 2
                    },
                    {
                        "source": 31,
                        "target": 9
                    },
                    {
                        "source": 32,
                        "target": 1
                    },
                    {
                        "source": 32,
                        "target": 25
                    },
                    {
                        "source": 32,
                        "target": 26
                    },
                    {
                        "source": 32,
                        "target": 29
                    },
                    {
                        "source": 33,
                        "target": 3
                    },
                    {
                        "source": 33,
                        "target": 9
                    },
                    {
                        "source": 33,
                        "target": 15
                    },
                    {
                        "source": 33,
                        "target": 16
                    },
                    {
                        "source": 33,
                        "target": 19
                    },
                    {
                        "source": 33,
                        "target": 21
                    },
                    {
                        "source": 33,
                        "target": 23
                    },
                    {
                        "source": 33,
                        "target": 24
                    },
                    {
                        "source": 33,
                        "target": 30
                    },
                    {
                        "source": 33,
                        "target": 31
                    },
                    {
                        "source": 33,
                        "target": 32
                    },
                    {
                        "source": 34,
                        "target": 9
                    },
                    {
                        "source": 34,
                        "target": 10
                    },
                    {
                        "source": 34,
                        "target": 14
                    },
                    {
                        "source": 34,
                        "target": 15
                    },
                    {
                        "source": 34,
                        "target": 16
                    },
                    {
                        "source": 34,
                        "target": 19
                    },
                    {
                        "source": 34,
                        "target": 20
                    },
                    {
                        "source": 34,
                        "target": 21
                    },
                    {
                        "source": 34,
                        "target": 23
                    },
                    {
                        "source": 34,
                        "target": 24
                    },
                    {
                        "source": 34,
                        "target": 27
                    },
                    {
                        "source": 34,
                        "target": 28
                    },
                    {
                        "source": 34,
                        "target": 29
                    },
                    {
                        "source": 34,
                        "target": 30
                    },
                    {
                        "source": 34,
                        "target": 31
                    },
                    {
                        "source": 34,
                        "target": 32
                    },
                    {
                        "source": 34,
                        "target": 33
                    }
                ]
            },
            config: {
                node: { //节点的默认配置
                    label: { //标签配置
                        show: true, //是否显示
                        color: '20,20,20', //字体颜色
                        font: 'normal 14px Arial', //字体大小及类型 
                        textPosition: 'Bottom_Center' //文字位置 Top_Center,Bottom_Center,Middle_Right,Middle_Center
                    },
                    shape: 'circle'
                },
                link: { //连线的默认配置
                    lineType: 'direct', //连线类型,direct,curver,vlink,hlink,vbezier,hbezier,bezier
                    colorType: 'source', //连线颜色类型 source:继承source颜色,target:继承target颜色 both:用双边颜色，defined:自定义
                    alpha: 1, // 连线透明度
                    showArrow: false, //显示连线箭头
                },
                wheelZoom: 0.8, //开启鼠标滚轮缩放
                highLightNeiber: true //相邻节点高亮开关
            },
        }
    },
    created() {
        this.drawGraphData()
    },
    methods: {
        // 获取所有的知识节点信息
        async drawGraphData() {
            this.createGraph()
            this.runLayout(this.visGraph.getGraphData())
            this.loading = false;
        },
        createGraph() {
            this.visGraph = new VisGraph(document.getElementById('graph-panel'), this.config)
            // this.visGraph.clearAll()
            this.visGraph.drawData(this.graphData)
        },
        runLayout(graphData) {
            this.layout = new LayoutFactory(graphData).createLayout('kk');
            this.layout.resetConfig({
                realSize: 1500 //区域大小
            });

            runLoopNum = 0;
            while (runLoopNum++ < 100) {
                this.layout.runLayout();//执行布局计算
            }
            this.visgraph.setZoom('auto');//自动缩放
        }

    }
}


</script>

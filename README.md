### Power Usage Calendar Card for Home Assistant
一个美观、功能强大的电力使用量日历卡片，用于在 Home Assistant 仪表板上直观展示电力消耗数据。

## ✨ 特性亮点
📅 日历视图：直观展示每日用电量和电费

📊 多维度分析：年、月、日三个时间维度的详细数据

🎨 图表可视化：使用 ECharts 提供专业的图表展示

💡 分时段统计：支持谷、峰、平、尖四个时段的电量统计

💰 费用计算：自动计算并显示电费金额

📱 响应式设计：完美适配桌面和移动设备

⚡ 数据缓存：5分钟缓存机制，减少数据刷新频率

🔍 交互详情：点击日期查看详细的用电分布

## 📸 界面预览

<div style="display: flex; justify-content: space-around; align-items: center; flex-wrap: wrap;">
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/%E5%B9%B4%E7%94%A8%E7%94%B5.png" alt="截图" style="width: 30%; height: auto; margin: 5px;">
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/%E6%97%A5%E5%8E%86%E5%BC%B9%E7%AA%97.png" alt="截图" style="width: 30%; height: auto; margin: 5px;">
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/%E6%97%A5%E7%94%A8%E7%94%B5.png" alt="截图" style="width: 30%; height: auto; margin: 5px;">  
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/%E6%9C%88%E7%94%A8%E7%94%B5.png" alt="截图" style="width: 30%; height: auto; margin: 5px;">  
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/%E7%94%A8%E7%94%B5%E6%97%A5%E5%8E%86.png" alt="截图" style="width: 30%; height: auto; margin: 5px;">  
  <img src="https://github.com/chjspp520/power-usage-calendar-card/blob/main/power-usage-calendar-card%E6%BC%94%E7%A4%BA.mp4" alt="演示视频" style="width: 30%; height: auto; margin: 5px;">  


  
## 🚀 安装方法
手动安装
将 power-usage-calendar-card.js 文件复制到 Home Assistant 的 www 目录

在仪表板配置中添加资源引用：

```yaml
resources:
  - url: /local/power-usage-calendar-card.js
    type: module
```
## 🛠️必要组件

1、国家电网组件

2、国家电网辅助信息组件   https://github.com/xiaoshi930/state_grid_info

3、echarts.min.js库，自动从cdn加载https://cdn.jsdelivr.net/npm/echarts@5.4.3/dist/echarts.min.js

如果不安装以上1、2个组件将无法运行，也可以使用自定义实体的状态属性作为数据来源，数据结构如下：
```yaml
{
  "daylist": [
    {
      "day": "2024-01-01",
      "dayEleNum": 15.5,
      "dayEleCost": 8.53,
      "dayVPq": 5.2,
      "dayPPq": 6.3,
      "dayNPq": 3.5,
      "dayTPq": 0.5
    }
  ],
  "monthlist": [
    {
      "month": "2024-01",
      "monthEleNum": 450.5,
      "monthEleCost": 247.78,
      "monthVPq": 150.2,
      "monthPPq": 180.3,
      "monthNPq": 100.5,
      "monthTPq": 19.5
    }
  ],
  "yearlist": [
    {
      "year": "2024",
      "yearEleNum": 5400.5,
      "yearEleCost": 2970.28,
      "yearVPq": 1800.2,
      "yearPPq": 2160.3,
      "yearNPq": 1200.5,
      "yearTPq": 239.5
    }
  ]
}
```


##  ⚙️ 配置示例
```yaml
type: custom:power-usage-calendar-card
entity: sensor.power_usage_stats
title: 家庭用电统计
hide_title: false
width: 400px
```

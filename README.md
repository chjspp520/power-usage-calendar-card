Power Usage Calendar Card for Home Assistant
一个美观、功能强大的电力使用量日历卡片，用于在 Home Assistant 仪表板上直观展示电力消耗数据。

✨ 特性亮点
📅 日历视图：直观展示每日用电量和电费

📊 多维度分析：年、月、日三个时间维度的详细数据

🎨 图表可视化：使用 ECharts 提供专业的图表展示

💡 分时段统计：支持谷、峰、平、尖四个时段的电量统计

💰 费用计算：自动计算并显示电费金额

📱 响应式设计：完美适配桌面和移动设备

⚡ 数据缓存：5分钟缓存机制，减少数据刷新频率

🔍 交互详情：点击日期查看详细的用电分布

📸 界面预览



🚀 安装方法
手动安装
将 power-usage-calendar-card.js 文件复制到 Home Assistant 的 www 目录

在仪表板配置中添加资源引用：

```yaml
resources:
  - url: /local/power-usage-calendar-card.js
    type: module


📸 界面预览
    
⚙️ 配置示例
yaml
type: custom:power-usage-calendar-card
entity: sensor.power_usage_stats
title: 家庭用电统计
hide_title: false
width: 400px
配置选项
参数	类型	默认值	说明
entity	string	必填	提供数据的传感器实体
title	string	"电力使用量日历"	卡片标题
hide_title	boolean	false	是否隐藏标题
width	string	"400px"	卡片宽度

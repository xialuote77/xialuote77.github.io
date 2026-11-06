# 吕昆泽 Kunze Lyu · 个人网站

纯静态网站，无需构建：`index.html` 包含中英双语内容、动画和内联 SVG 图表，`assets/` 保存区域地图及图表数据来源。

## 本地预览
双击 `index.html`，或在本文件夹运行 `python3 -m http.server`，打开 http://localhost:8000

## 部署到 GitHub Pages
网站从 `main` 分支的根目录部署，访问 https://xialuote77.github.io 。

## 修改
- 中英文内容：每段文字都有 `<span lang="zh">` 和 `<span lang="en">` 两份。
- 颜色和字体：`<style>` 顶部的 `:root` 变量。
- 箱线图使用深紫 `#5B3BC4` 与亮紫 `#A78BFA`。
- 原生图表的数据同时嵌入首页并保存在 `assets/taxi-chart-data.json`；修改数据时保持两处一致。
- 动效支持暂停，并尊重系统减少动态效果设置；指标数值直接显示最终值。

## 出租车图表来源
误差箱线图、出发时段折线图和时长分布直方图采用内联 SVG，支持悬停、点选、左右方向键和 Home / End。区域地图保留图片。

来源为 [nyc-airport-taxi-travel-time 的固定提交](https://github.com/xialuote77/nyc-airport-taxi-travel-time/tree/639e70614215291f3319bc979e9e2a7fe628b5f2)。该提交未单独导出三张图的数值表；当前绘图数值由原始 PDF 矢量坐标与坐标轴刻度恢复，属于近似绘图读数，并非重新执行数据管道的结果。页面标注近似值并提供原图链接；JSON 保存来源链接和原文件 SHA-256。

- 箱线图：2024 年 6 月留出测试集；箱体为 Q1–Q3，中线为中位数，须线为样本 P5–P95，按原图省略离群点。
- 时段图：2024 年 1–6 月有效机场行程，各机场 24 个小时的中位数与 P95。
- 分布图：2 分钟区间，显示 0–120 分钟；分母是各机场全部有效行程，不重新归一化可见区间。极小非零占比显示为 `< 0.01%`。
- 样本数来自同一提交的 `tables/travel_time_summary.tex`：JFK 178,594，LaGuardia 222,348。

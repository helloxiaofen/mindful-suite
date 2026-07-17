# 三件小事 · mindful-suite

三个纯前端小程序（HTML/CSS/JS，无需构建、无需后端），可直接部署到 GitHub Pages，也可以在 iPhone Safari 中「添加到主屏幕」当 App 用。

```
mindful-suite/
├─ index.html             # 总入口
├─ meditation/index.html  # 呼吸冥想
├─ diary/index.html       # 碎碎念日记
└─ tracker/index.html     # 搞钱日历
```

## 1. 呼吸 · 冥想 (`meditation/`)
- 吸气 4s（放大）→ 屏息 1.2s → 呼气 5s（缩小），**3 次呼吸为一个循环**，圆点显示循环内进度
- 计时器记录本次练习时长；停止后自动写入当天累计时长
- 首页三张统计卡：今日累计分钟 / 累计练习次数 / 连续坚持天数，做出**积累感**
- 支持一键**导出 CSV** 练习记录

## 2. 碎碎念日记 (`diary/`)
- 顶部日期跟随系统时间自动更新
- 每天从题库固定抽取**一个每日问题**，同一天不变，第二天自动换新
- 输入内容 500ms 防抖自动保存到本地，**刷新页面不会丢失**，切走 / 关闭页面也会强制保存
- 「生成今日日记」把问答 + 自由书写自动整理成一篇带日期抬头的格式化日记
- 历史面板可浏览过往日记，支持单篇导出或**导出全部日记**为 .txt
- 表情包贴纸风背景 + 手写字体，营造可爱的日记本质感

## 3. 搞钱日历 (`tracker/`)
- 面向自媒体、电商、写作交付三条赚钱线，记录每天完成事项数 + 收入
- 首页大卡片：今日收入 / 累计收入 / 累计完成事项 / 连续记录天数
- 近 7 天收入柱状图、三条业务线的累计收入进度条
- 支持导出 CSV，可直接用 Excel / 飞书表格打开

## 数据存储说明
三个小程序都使用浏览器的 `localStorage` 保存数据，**只保存在当前设备的浏览器里，不会上传到任何服务器**。换设备或清除浏览器数据会导致记录丢失，建议定期使用各自的「导出」功能备份。

## 部署到 GitHub Pages
```bash
# 1. 在 GitHub 新建一个空仓库，例如 mindful-suite（不要勾选自动生成 README）
cd mindful-suite
git remote add origin git@github.com:你的用户名/mindful-suite.git
git branch -M main
git push -u origin main

# 2. 打开仓库 Settings → Pages → Source 选择 main 分支 / root 目录
# 3. 几分钟后即可通过 https://你的用户名.github.io/mindful-suite/ 访问
```

## 添加到 iPhone 主屏幕（推荐体验）
用 Safari 打开对应链接 → 点击底部「分享」→「添加到主屏幕」，图标会像原生 App 一样出现在桌面，点开直接全屏、无地址栏，写日记「打开图标就能写」。

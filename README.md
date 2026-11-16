# 无线输电 AR 教具（软件部分）

## 文件
- `index.html`：AR 模式，带慢动作交流动画。网址后面加 `#preview` 是 3D 仿真（不用摄像头）。
- `sim.html`：2D 仿真。
- `base-templates-A4.pdf`：两块线圈底板的 1:1 模板（含 Marker 和线圈位置线），A4、100% 实际大小打印。
- `marker-tx.png` / `marker-rx.png`：单张 Marker 图片（黑框 4 cm）。
- `data/`：Marker 识别数据，不要改名或删除。

## 部署
把这个文件夹里的全部内容上传到一个公开的 GitHub 仓库，在 Settings → Pages 里发布。
摄像头只能在 HTTPS 网址下使用；手机上用 Chrome（Android）或 Safari（iPhone）打开。

## 搭建
1. 打印 `base-templates-A4.pdf`，沿灰色边框剪下 TX 和 RX 两块模板，各贴在一块硬底板上（约 6.6 × 11 cm）。
2. 线圈立在模板的粗黑线上：线圈中心对准长刻度，线圈平面沿着粗线，用热熔胶固定。
3. TX 底板放左边，RX 底板放右边，粗线一侧互相靠近。Marker 在线圈前方（朝向自己的一侧）。
4. 电池和电路放在 TX 底板后方或外侧，导线不要压在 Marker 上。
5. 推 RX 底板时捏它的后半部分，不要用手盖住 Marker。

## 网页设置
用模板搭的话，只需要改两处：线圈直径，以及“线圈中心离桌面高度”（线圈半径加底板厚度）。
其余默认值已经和模板一致：Marker 黑框 4 cm，线圈在 Marker 后方 4 cm、比 Marker 中心更靠内侧 3 cm。

## 校准
实物做好后，量出 LED 刚好熄灭的距离，调“TX 线圈电压幅值 V₁”，让预测在同一距离熄灭。

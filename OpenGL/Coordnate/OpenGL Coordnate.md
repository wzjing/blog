# OpenGL 坐标系
## 坐标系种类：
* 物体坐标 Object(Module) Coordinates
<br>对象的本地坐标系
* 世界坐标 World Coordinates
<br>OpenGL三维世界的坐标系，屏幕中心为(0,0,0)，x轴向右，y轴向上，z轴指向屏幕外，范围[-1, -1]-[1, 1]。
* 眼坐标 Eye(Camera) Coordinates
<br>以观察者视线正前方为Z+方向。
* 裁剪坐标 Clip Coordinates
<br>裁剪体坐标系
* 标准化设备坐标 Normalized Device Coordinates(NDC)
<br>统一规范化的设备坐标，便于在不同设备上显示一致效果。
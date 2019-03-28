- glEnable(GL_BLEND)

开启颜色混合模式。需要使用透明度时，则开启此选项

- glBendFunc(sfactor, dfactor)

颜色混合的方式，sfactor表示选取的原颜色的因子，dfactor表示选取的目标颜色的因子。如glBlendFunc(GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA)，使用原颜色的alpha作为因子，目标颜色使用(1-原颜色alpha)的方式叠加

- glEnable(GL_DEPTH_TEST)

开启深度测试，此选项表示被遮挡的像素不会被绘制，如果需要绘制透明则需要关闭此选项。

- glDepthFunc(cap)

执行深度测试的比较方式，如glDepthFunc(GL_LESS)表示如果目标深度值小于原深度则通过，也就是仅绘制离镜头更近的像素。
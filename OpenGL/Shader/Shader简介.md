# OpenGL Shader 简介
> OpenGL 2.0中引入了可编程式渲染管线的设计概念，其中用于实现渲染管线编程的脚本就是Shader(着色器)。最初版本的OpenGL包括两个Shader：Vertex Shader(顶点着色器), Fragment Shader(片元着色器)，后续又添加了多种Shader类型，但是最核心的只有这两个。OpenGL中Shader所使用的语言叫做GLSL语言，是一种类似于C的语言。

- ### 版本对应
|GLSL|OpenGL|
|:--:|:--:|
|#version 110|2.0|
|#version 120|2.1|
|#version 130|3.0|
|#version 140|3.1|
|#version 150|3.2|
|#version 330|3.3|
|#version 400|4.0|
|#version 410|4.1|
|#version 420|4.2|
|#version 430|4.3|
|#version 440|4.4|
|#version 450|4.5|
|#version 460|4.6|

|GLSL ES|OpenGL ES|WebGL|说明|
|:--:|:--:|:-:|:--:|
|#version 100 es|2.0|1.0|基于GLSL 1.20|
|#version 300 es|3.0|2.0|给予GLSL 3.30|

- Vertex Shader

顶点着色器负责绘制模型中的各个顶点
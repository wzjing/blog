# GLSL简介

- ## GLS语言
GLSL是一个类似于C的语言，其中大部分语法都与C语言基本一致，但是没有C语言的标准库和内存管理等功能，GLSL内置了大量的数学运算函数和数学类型用于计算

- ## 基本类型

    **int**：整型

    **float**：为了简化开发，GLSL只有一种float类型，float的精度可以在GLSL文件的开头显式的指定：
    ```C
    // 根据用途设置不同的精度，以优化性能
    precision highp float; // 高精度，可提供更好的效果
    precision mediump float; // 中等精度
    precision lowp float; // 低精度，牺牲效果以提升更快的速度
    ```

    **bool**：布尔值

- ## 向量

    **vec2**：二元结构[x, y]
    ```C
    vec2 v2(1.0, 2.0);

    float x = v2.x; 
    float y = v2.y;
    vec2 coordinate = v2.xy; //可以使用这种方式表示一个vec2变量
    ```
    **vec3**：三元结构[x, y, z]

    ```C
    vec2 v3(1.0, 2.0, 3.0);

    float x = v3.x;
    float y = v3.y;
    float z = v3.z;
    ```
    **vec4**：四元结构[x, y, z, w]或[r, g, b, a]或[s, t, p, q]

    ```C
    vec2 v4(1.0, 2.0, 3.0， 4.0);

    float x = v4.x; // v4.x == v4.r == v4.s
    float y = v4.y; // v4.y == v4.g == v4.t
    float z = v4.z; // v4.z == v4.b == v4.p
    float w = v4.w; // v4.w == v4.a == v4.q
    ```
    向量之间以及向量和实数之间的数学运算都是有意义的：
    ```C
    vec2 v2(1.0, 2.0);
    vec3 v3(v2, 3.0); // v3 is (1.0, 2.0, 3.0)
    vec4 v4(v3, 4.0); // or (v2, 3.0, 4.0)

    vec2 v21 = 1.0 - v2; // v21 is (0.0, -1.0)
    vec2 v22 = 2 * v2; // v22 is (2.0, 4.0)
    vec3 v31 = v3 - v2; // v31 is (0.0, 0.0, 3.0)
    ```

- ## 矩阵

    **mat2**：二阶矩阵 2x2
    ```C
    mat2 m2 = mat2(1.0, 1.1, 2.0, 2.1);
    mat2 m21 = mat2(1.0); // m21 is (1.0, 0.0, 0.0, 1.0);
    ```
    
    **mat3**：三阶矩阵 3x3
    ```C
    vec3 v3(1.0, 2.0, 3.0);
    mat3 m3 = mat3(v3, v3, v3); // use vector fill a matrix
    ```

    **mat4**：四阶矩阵 4x4
    ```C
    mat2 m2 = (1.0);
    mat4 m4 = mat4(m2, m2, m2, m2); // use one matrix fill another
    ```

- ## 

- ## 修饰符

    ****
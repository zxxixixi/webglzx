####一.模板
 1. 创建标签
 2. 获取标签
 3. 获取wenGL上下文---getContext('webgl')
 4. 顶点着色器源码
 5. 片元着色器源码
 6. 初始化着色器
        1. 创建顶点和片元着色器对象--createShader
        2. 引入顶点和片元着色器源代码--shaderSource
        3. 编译顶点和片元着色器--compileShader

        4. 创建程序对象--createProgram
        5. 附着顶点着色器和片元着色器到program--attachShader
        6. 链接program--linkProgram
             使用程序之前可---> getAttribLocation createBuffer bindBuffer bufferData  viewport  clearColor  clear
        7. 使用program--useProgram
             使用程序之后可---> enableVertexAttribArray bindBuffer vertexAttribPointer

 7. 开始绘制，显示器显示结果--drawArrays


####顶点着色器需要的数据，可以通过一下三点获取：
1.Attributes属性（从缓冲中获取的数据）
2.Uniforms全局变量（在一次绘制中对所有顶点保持一致值）
3.Textures纹理（从像素或纹理元素中获取的数据）

片断着色器所需的数据，可以通过以下三种方式获取
1.Uniforms全局变量
2.Textures纹理
3.Varying全局变量

####GLSL全称是 Graphics Library Shader Language （图形库着色器语言），是着色器使用的语言。 它有一些不同于JavaScript的特性，主要目的是为栅格化图形提供常用的计算功能。 所以它内建的数据类型例如vec2, vec3和 vec4分别代表两个值，三个值和四个值， 类似的还有mat2, mat3 和 mat4 分别代表 2x2, 3x3 和 4x4 矩阵。 你可以做一些运算例如常量和矢量的乘法。

v.x 和 v.s 以及 v.r ， v[0] 表达的是同一个分量。
v.y 和 v.t 以及 v.g ， v[1] 表达的是同一个分量。
v.z 和 v.p 以及 v.b ， v[2] 表达的是同一个分量。
v.w 和 v.q 以及 v.a ， v[3] 表达的是同一个分量。

v.bgra和vec4(v.b, v.g, v.r, v.a)是一样的
v.yyyy和vec4(v.y, v.y, v.y, v.y)是一样的
vec4(v.rgb, 1)和vec4(v.r, v.g, v.b, 1)是一样的
vec4(1)和vec4(1, 1, 1, 1)是一样的
vec4 s = sin(v)和vec4 s = vec4(sin(v.x), sin(v.y), sin(v.z), sin(v.w))一样
vec4 m = mix(v1, v2, f)
和
vec4 m = vec4(
  mix(v1.x, v2.x, f),
  mix(v1.y, v2.y, f),
  mix(v1.z, v2.z, f),
  mix(v1.w, v2.w, f))
一样

GLSL是一个强类型的语言*******
float f = 1;  // 错误，1是int类型，不能将int型赋值给float
float f = 1.0;      // 使用float
float f = float(1)  // 转换integer为float
vec4(v.rgb, 1) 不会因为 1 报错，因为 vec4 内部进行了转换类似 float(1)

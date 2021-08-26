一.模板
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

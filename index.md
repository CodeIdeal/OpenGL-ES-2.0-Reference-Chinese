## OpenGL® ES 2.0 参考文档
>我写这份文档的翻译是因为在我学习OpenGL ES 2.0的过程中，针对对于诸多android.opengl.GLES20.xxx 静态常量及方法的含义及作用感到迷惑。而在互联网中又搜索不到全面且可信的相关中文翻译，所以才有了这个项目的存在。在翻译中，我会尽量的在学习相关的接口后，结合[原文](https://www.khronos.org/registry/OpenGL-Refpages/es2.0/)对这些api doc信息(包括参数、返回值、错误条件和相关命令的描述)尽量通俗易懂的进行翻译。  


## 方法快查表：

|  [C](#C)  | V |
| --- | ---|
| [glClear](#glclear) | [glViewport] |
| [glCreateShader] | more... |


## A

## B

## C

### glClear

#### 名称

glClear — 将缓冲区清除为预设值

#### C 规范

void glClear(	GLbitfield mask);
 
#### 参数

`mask`  
指示要清除的缓冲区的掩码，从而进行按位或操作。这三个掩码是GL_COLOR_BUFFER_BIT，GL_DEPTH_BUFFER_BIT和GL_STENCIL_BUFFER_BIT。

#### 描述  
`glClear` 将窗口的位面区域设置为之前由 glClearColor、glClearDepthf 和 glClearStencil 选择的值。

像素所有权测试、剪刀测试、抖动和缓冲区写入掩码会影响glClear的操作。剪刀盒会对被清除的区域进行约束。glClear会忽略混合功能、模板、碎片着色和深度缓冲。

`glClear` 取一个单一的参数，是几个值的位数OR，表示要清除哪个缓冲区。

缓冲区的掩码分别为:

`GL_COLOR_BUFFER_BIT`  
表示当前启用的颜色写入缓冲区。

`GL_DEPTH_BUFFER_BIT`  
表示深度缓冲区。

`GL_STENCIL_BUFFER_BIT`  
表示钢网缓冲区。

每个缓冲区的清除值取决于该缓冲区分别由`glClearColor`、`glClearDepthf` 和 `glClearStencil` 方法设置的值。

#### Notes
如果一个缓冲区不存在，那么针对该缓冲区的glClear就没有效果。

#### Errors
如果在掩码中设置了三个定义位以外的任何位，就会产生`GL_INVALID_VALUE`。

#### Associated Gets
glGet with argument `GL_DEPTH_CLEAR_VALUE`

glGet with argument `GL_COLOR_CLEAR_VALUE`

glGet with argument `GL_STENCIL_CLEAR_VALUE`

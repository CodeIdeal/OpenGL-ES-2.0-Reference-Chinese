## OpenGL® ES 2.0 参考文档
>我写这份文档的翻译是因为在我学习OpenGL ES 2.0的过程中，针对对于诸多android.opengl.GLES20.xxx 静态常量及方法的含义及作用感到迷惑。而在互联网中又搜索不到全面且可信的相关中文翻译，所以才有了这个项目的存在。在翻译中，我会尽量的在学习相关的接口后，结合[原文](https://www.khronos.org/registry/OpenGL-Refpages/es2.0/)对这些api doc信息(包括参数、返回值、错误条件和相关命令的描述)尽量通俗易懂的进行翻译。  <div style="text-align: right"> ——写在前面 </div>


## 方法快查表：

|  C  | V |
| --- | ---|
| [glClear] | [glViewport] |
| [glCreateShader] | more... |


## A

## B

## C

### glClear

#### Name

glClear — clear buffers to preset values

#### C Specification

void glClear(	GLbitfield mask);
 
#### Parameters

`mask`  
Bitwise OR of masks that indicate the buffers to be cleared. The three masks are GL_COLOR_BUFFER_BIT, GL_DEPTH_BUFFER_BIT, and GL_STENCIL_BUFFER_BIT.

#### Description  
glClear sets the bitplane area of the window to values previously selected by glClearColor, glClearDepthf, and glClearStencil.

The pixel ownership test, the scissor test, dithering, and the buffer writemasks affect the operation of glClear. The scissor box bounds the cleared region. Blend function, stenciling, fragment shading, and depth-buffering are ignored by glClear.

glClear takes a single argument that is the bitwise OR of several values indicating which buffer is to be cleared.

The values are as follows:

`GL_COLOR_BUFFER_BIT`  
Indicates the buffers currently enabled for color writing.

`GL_DEPTH_BUFFER_BIT`  
Indicates the depth buffer.

`GL_STENCIL_BUFFER_BIT`  
Indicates the stencil buffer.

The value to which each buffer is cleared depends on the setting of the clear value for that buffer.

#### Notes
If a buffer is not present, then a glClear directed at that buffer has no effect.

#### Errors
GL_INVALID_VALUE is generated if any bit other than the three defined bits is set in mask.

#### Associated Gets
glGet with argument GL_DEPTH_CLEAR_VALUE

glGet with argument GL_COLOR_CLEAR_VALUE

glGet with argument GL_STENCIL_CLEAR_VALUE

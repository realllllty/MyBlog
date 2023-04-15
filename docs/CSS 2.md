margin: 0 auto;  
/*上下外边距为0,左右自适应*/

# 选择器
## 层次选择器
![[Pasted image 20230402111919.png]]
## 结构伪类选择器


# 定位
## relative
- 位置会按照==原本在文档流当中的位置进行调整==(这是和`position:absolute`不同的地方)
- `relative`仍然处于文档流当中,会占据原本在文档流当中的位置
- 相对定位元素的==位置偏移是相对于它的包含块(container block)进行计算的==。而包含块通常是元素的直接父元素。



# 单位
## rem单位
>==相当于是一种适配不同手机屏幕的一种方案==（因为不同手机型号的屏幕大小是有差异的）

font size of the root element （根元素的字体大小）


# Padding


## 通过Padding实现固定宽高比(图片等比例自适应布局)
实现方式:通过Padding控制父级元素的内容高度,再通过object-fit实现图片的等比例缩放
讲解:
面的列表内容宽度随着浏览器窗口的变大而变大，并且列表页面主要是图片+标题，需求又要保证图片的等比例缩放。
### 父级
==当元素的 padding（填充）内边距被清除时，所释放的区域将会受到元素背景颜色的填充==。 单独使用 padding 属性可以改变上下左右的填充。

假设现在有个`<div>`元素： div { padding-bottom: 100%; } 这样即可实现一个宽高1:1正方形。他的宽度无论改变多少，都能保持宽高1:1不变。
>在设置 padding-bottom: 100% 时，填充的高度将等于元素宽度的百分之百，因此元素的总高度将等于其内容的高度加上填充的高度。由于填充的宽度和元素的宽度相同，所以它会在元素的底部创建一个正方形的填充区域，但是元素的内容不会被挤压，因为它们可以在填充区域的上方自由放置。

### 子级(图片级)
图片高度计算公式
``(paddingbottom+paddingtop)/(paddingleft+paddingright)===img_height/img_width
- object-fit: cover;可以保持图片的等比例缩放
- 通过position:absolute确保内部图片不会影响到父级容器的布局


# Margin
**'margin-left' + 'border-left-width' + 'padding-left' + 'width' + 'padding-right' +'border-right-width' + 'margin-right' = width of containing block**
**margin-left = width of containing block - width(div)**

==margin: auto 水平居中的原理。==
>如果“margin left”和“margin right”都是“auto”，则它们使用的值相等。这使元素相对于包含块的边缘水平居中。

>margin-right 不设置的话默认是0，width 定宽之后，margin-left取值为 auto ，自动占据了剩余的全部宽度

margin-left = width of containing block - width(div)

# 移动元素上下左右
```css
margin-top: -20px; /* 向上移动20像素 */
```
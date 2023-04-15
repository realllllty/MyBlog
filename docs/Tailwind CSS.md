# 如何引入Tailwind CSS(重要)
[Vue中使用 Tailwind CSS - 掘金](https://juejin.cn/post/7216990794942201913)
# 自定义配置customize
如果需要仅仅只关注自己设置的规则而不是和tailwind自带规则进行混合。应当找到tailwind.config.js进行配置
配置实例：
![Store_picPasted image 20230406010249.png](https://matt-obstorage777-1313452829.cos.ap-shanghai.myqcloud.com/pic_store/Store_picPasted%20image%2020230406010249.png)

# 布局
## Boxsizing
使用box-border选项可以将元素的box-sizing设置为`border-box`

## Stacking

# 生产优化(to be continued)
构建生产--使用`purge`（清除）选项进行tree-shaking优化
## HTML可清除编写
PurgeCSS根据正则表达式匹配HTML类
因此不能够使用字符串连接来创建类名
正确写法：
`<div class="{{  error  ?  'text-red-600'  :  'text-green-600'  }}"></div>
`
>**解释一下purgecss和cssnano的区别**
>
>Purgecss和Cssnano都是用于优化和压缩CSS文件的工具，但它们有不同的功能和应用场景。
>==Purgecss是一个用于删除未使用CSS代码的工具，它可以扫描整个项目，并通过分析HTML、JS和Vue等文件中的类名和选择器来确定哪些CSS代码被使用，然后从CSS文件中删除未使用的代码。==这可以帮助减少CSS文件的大小，并提高页面加载速度。Purgecss特别适合于大型项目和框架，因为这些项目通常会包含大量未使用的CSS代码。
>==Cssnano是一个用于优化和压缩CSS代码的工具，它可以通过删除注释、空格、未使用的代码和重复的规则等来减小CSS文件的大小，并优化CSS代码的结构和性能。==Cssnano可以用于任何大小的项目，并且可以与其他构建工具和流程集成。简而言之，Purgecss的重点是删除未使用的CSS代码，而Cssnano的重点是优化和压缩CSS代码。这两个工具可以一起使用，以进一步减小CSS文件的大小并提高性能。

>**cssnano对于使用tailwindcss进行构建的项目有效吗**
>是的，cssnano对于使用Tailwind CSS进行构建的项目同样有效。
>虽然Tailwind CSS已经对CSS文件进行了优化和压缩，但是在构建和部署项目时，使用cssnano可以进一步压缩和优化CSS代码，以减小文件大小并提高性能。cssnano可以帮助删除未使用的CSS代码、优化选择器和属性、压缩颜色和字体名称等，这些都有助于减小CSS文件的大小并提高页面加载速度。
>因此，在使用Tailwind CSS构建项目时，建议在构建流程中使用cssnano来优化和压缩生成的CSS文件。


# position:sticky粘性布局实现table表格固定任意行或列
table表格中当展现的数据项目非常多，表格结构异常复杂时，浮动显示（首）行或（首）列是用户体验非常好的展现方式
## position:sticky的使用
基于用户的滚动位置来定位  
这是一个结合了 position:relative 和 position:fixed 两种定位功能于一体的特殊定位
```
{
  position:sticky;
  top: 0; /*阈值top, right, bottom 或 left 之一*/
}
```
> 该元素并不脱离文档流，仍然保留元素原本在文档流中的位置。
> 当元素在容器中被滚动超过指定的偏移值时，元素在容器内固定在指定位置。亦即如果你设置了top: 50px，那么在sticky元素到达距离相对定位的元素顶部50px的位置时固定，不再向上移动。

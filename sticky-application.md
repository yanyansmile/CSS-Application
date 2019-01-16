# position:sticky粘性布局实现table表格固定任意行或列
table表格中当展现的数据项目非常多，表格结构异常复杂时，浮动显示（首）行或（首）列是用户体验非常好的展现方式
## sticky的使用
基于用户的滚动位置来定位  
这是一个结合了 position:relative 和 position:fixed 两种定位功能于一体的特殊定位  
**目标标签一定要选择到th、td，而不是tr**
```
{
  position:sticky;
  top: 0; 
}
```
#### 使用条件：
1.父元素不能overflow:hidden或者overflow:auto属性  
2.必须指定top、bottom、left、right4个值之一，否则只会处于相对定位  
3.父元素的高度不能低于sticky元素的高度  
4.sticky元素仅在其父元素内生效  

> 该元素并不脱离文档流，仍然保留元素原本在文档流中的位置。
> 当元素在容器中被滚动超过指定的偏移值时，元素在容器内固定在指定位置。亦即如果你设置了top: 50px，那么在sticky元素到达距离相对定位的元素顶部50px的位置时固定，不再向上移动。

兼容性 [点击查看>>](https://caniuse.com/#search=sticky)

## sticky示例
css代码  
```
<style>
        table {
            height: 500px;
            background: #f2f2f2;
        }
        /* 选取表格第一行 */
        table tr:first-of-type>th {
            position: sticky;
            width: 50px;
            min-height: 50px;
            background: #baf124;
            top: 0;
        }
        /* 设置表格首行层级 */
        table tr:first-of-type>th:first-of-type {
            z-index: 999999;
        }
        /* 选取表格第一列 */
        table tr>th:nth-child(1),
        tr>td:nth-child(1) {
            position: sticky;
            left: 0;
            background: #249ff1;
            width: 50px;
        }
    </style>
```
html代码  
```
<table>
        <tr>
            <th>name one</th>
            <th>name two</th>
            <th>name three</th>
            <th>name four</th>
            <th>name five</th>
        </tr>
        <!-- 请自行复制任意多行 -->
        <tr>
            <td>单元格</td>
            <td>单元格</td>
            <td>单元格</td>
            <td>单元格</td>
            <td>单元格</td>
        </tr>
    </table>
```




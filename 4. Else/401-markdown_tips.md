# markdown 常用语法
## 标题
标题能显示出文章的结构。  
```
# Header 1  
## Header 2  
### Header 3  
#### Header 4  
##### Header 5  
###### Header 6  
```
## 文本样式
链接 : `[Title](URL)`  
加粗 : `**Bold**`  
斜体字 : `*Italics*`  
高亮 : `==text==`  
段落 : 段落之间空一行  
换行符 : 一行结束时输入两个空格  
列表 : `*` 添加星号成为一个新的列表项  
引用 : `>` 引用内容  
内嵌代码 :  `alert('Hello World');`  
画水平线 (HR) : `--------`  
方框： `- [ ] -`  

## 图片
`![]()`  
`![title](address)`  
图片位置、大小均不可调节

使用 html 的方法：  
`<img src="/assress" height="100" width="100">`  
`<img src="address" width="50%" height="50%">`  
eg.  
`<img src="/_posts/pic/image101.png" height="360" width="500"> `  
`<img src="https://github.com/101.png?raw=true" width="50%" height="50%" />`  
## 脚注
`[^1]: 这里是脚注的内容`   
[^1]: 这里是脚注的内容  
这里是脚注[^n]  
`[^n]: 这里是脚注的内容`  
[^n]: 这里是脚注的内容  
## 代码
单行注释 `alert('Hello World')`   
多行注释 3个`  
```language
contens
```  
eg.  
```c++
#include<iostream>
using namespace std;
int main(){
    int a = 0;
    cout<<"hello world"<<endl;
    return 0;
}
```  
## 列表格式
This paragraph contains a list of items.  
* Item 1   
* Item 2   
* Item three  

### 引用文本 quote     
> That is pulled out like this from the text my post.  

## Markdown编辑器
### OSX
`VSCode, Atom, Byword, Mou, Typora, MacDown, RStudio`
### Linux
`VSCode, Atom, Typora, ReText, UberWriter, RStudio`
### Windows
`VSCode, Atom, CuteMarkEd, MarkdownPad2, Miu, Typora, RStudio, iOS, Byword`
### 浏览器插件
`MaDo (Chrome), Marxico（Chrome）`
### 高级应用
`Sublime Text 3 + MarkdownEditing`
# Less 编写规范

1. 运算规范

  - 运算符前后统一加一个空格

  - 注意运算单位，单位同时参与运算，乘除运算时需要特别注意，注： 10px 不等于 10

  ```less
    // 正确的运算格式
  .jdc {
      width: 100px - 50px;
      width: 100px + 50px;
      width: 100px * 2;
      width: 100px / 2;
  }
  ```

2. mixin 名; 使用 `mx-` 开头。如: `mx-btn`

3. Extend 名: 使用 `-ext` 结尾

4. 推荐属性书写顺序: 显示属性	-> 自身属性	-> 文本属性和其他修饰

5. 使用变量命名常用的数字和颜色

6. 注释: 多组件放在同一文件内时，组件与组件间样式使用注释将其分开。
  - 建议使用行注释代替块注释。
  - 建议注释独占一行。避免行末注释。
  - 给没有自注释的代码写上详细说明，比如：

    > 为什么用到了 z-index
    例如，// modals are 6000, saving messages are 5500, header is 2000
      兼容性处理或者针对特定浏览器的 hack;

    - z-index: 不要设置巨大的数值, 比如: 100000, 99999, 这样大的数, 建议 100 内;

7. 列表型属性值 书写在单行时, 后必须跟一个空格。

  ```css
    font-family: Arial, sans-serif
  ```

8. 每行不得超过 50 个字符，除非单行不可分割。

9. 当一个 `rule` 包含多个 `selector` 时，每个选择器声明必须独占一行。

  ```css
  .post,
  .page,
  .comment {
      line-height: 1.5;
  }
  ```

10. 属性选择器中的值必须用双引号包围。

  ```css
    /* good */
  article[character="juliet"] {
      voice-family: "Vivien Leigh", victoria, female;
  }
  ```

11. 属性定义必须另起一行。

  ```css
  /* good */
  .selector {
      margin: 0;
      padding: 0;
  }
  ```
12. 属性定义后必须以分号结尾。

  ```css
  /* good */
  .selector {
      margin: 0;
  }
  ```

13. 推荐选择器的嵌套层级应不大于 3 级，位置靠后的限定条件应尽可能精确

14. url() 函数中的路径加引号
  ```css
    background: url('bg.png');
  ```

15. 长度为 0 时须省略单位。

16. RGB颜色值必须使用十六进制记号形式 #rrggbb。少使用 rgb(),

  * 带有alpha的颜色信息可以使用 rgba()。使用 rgba() 时每个逗号后必须保留一个空格。

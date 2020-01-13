# react 相关规范

1. React 组件使用帕斯卡命名，引用实例采用驼峰命名, 组件名称应该和文件名一致: `eslint: react/jsx-pascal-case`

  ```jsx
    import ReservationCard from './ReservationCard;

    const reservationItem = <ReservationCard />;
  ```

2. 为 JSX 语法使用下列的对其方式: `eslint: react/jsx-closing-bracket-location`

  ```jsx
    // good
  <Foo
    superLongParam="bar"
    anotherSuperLongParam="baz"
  />

  // 如果组件的属性可以放在一行就保持在当前一行中
  <Foo bar="bar" />
  // 多行属性采用缩进
  <Foo
    superLongParam="bar"
    anotherSuperLongParam="baz"
  >
    <Quux />
  </Foo>
  ```

3. JSX 的属性都采用`双引号`，其他的 JS 都使用`单引号`。`eslint: jsx-quotes`

  ```jsx
  // good
  <Foo bar="bar" />
  // good
  <Foo style={{ left: '20px' }} />
  ```


4. 属性名称始终使用驼峰命名法。

  ```jsx
    // good
  <Foo
    userName="hello"
    phoneNumber={12345678}
  />
  ```

5. 当属性值等于`true`的时候，省略该属性的赋值。` eslint: react/jsx-boolean-value`

  ```jsx
    // good
  <Foo
    hidden
  />
  ```

6. 用括号包裹`多行 JSX` 标签。 `eslint: react/wrap-multilines`

  ```jsx
  // good
  render() {
    return (
      <MyComponent className="long body" foo="bar">
        <MyChild />
      </MyComponent>
    );
  }
  ```

7. 当标签没有子元素时，始终时候自闭合标签。 `eslint: react/self-closing-comp`

  ```jsx
    // good
    <Foo className="stuff" />
  ```

8. 如果控件有多行属性，关闭标签要另起一行。 `eslint: react/jsx-closing-bracket-location`

  ```jsx
  // good
  <Foo
    bar="bar"
    baz="baz"
  />
  ```

9. 在 render 方法中事件的回调函数，应该在构造函数中进行bind绑定。 `eslint: react/jsx-no-bind`, 或者使用 `@autobind` 进行事件处理方法与this的绑定。

```jsx
   // good
  class extends React.Component {
    constructor(props) {
      super(props);

      this.onClickDiv = this.onClickDiv.bind(this);
    }

    onClickDiv() {
      // do stuff
    }

    render() {
      return <div onClick={this.onClickDiv} />
    }
  }
```

```jsx
// @autobind
  class Foo {
      @autobind
      onClick(e) {
          // ...
      }
  }
```

10. React 组件的内部方法命名不要使用下划线前缀。


11. isMounted: 不要使用 isMounted. `eslint: react/no-is-mounted` , 会被官方弃用,

12. key 属性设置: 渲染多个同类型组件时，必须加上key，如无特殊用途key值统一为组件名_+下标，如：key = { `submenu_${idx}` },

13. Refs 提供了一种方式，允许我们访问 DOM 节点或在 render 方法中创建的 React 元素 。我们推荐使用 createRef API 的方式

14. `建议`使用`withXxx`或`xxxable`形式的词作为高阶组件的名称。

  - 高阶组件是为组件添加行为和功能的函数，因此使用如上形式的词有助于对其功能进行理解。

15. 建议按照以下顺序编排组件中的方法和属性：

  ```txt
  static propTypes
  static contextTypes
  state defaultProps
  static state
  其它静态的属性
  用于事件处理并且以属性的方式（onClick = e => {...}）声明的方法
  其它实例属性
  constructor
  getChildContext
  componentWillMount
  componentDidMount
  shouldComponentUpdate
  componentWillUpdate
  componentDidUpdate
  componentWillUnmount
  事件处理方法
  其它方法
  render

  其中shouldComponentUpdate和render是一个组件最容易被阅读的函数，因此放在最下方有助于快速定位。
  ```

16. 建议使用箭头函数声明函数组件。

17. 推荐除`顶层`或`路由级组件`以外，所有组件均在概念上实现为`纯组件`（Pure Component）。

18. 禁止为继承自`PureComponent`的组件编写`shouldComponentUpdate`实现。

19. 建议将`JSX的层级`控制在`3层`以内。
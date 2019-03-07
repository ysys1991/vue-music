# ES6

## let 和 const

### let
  1、声明的变量 仅在块级作用域内有效
  2、不存在变量名提升
  3、暂时性死区：在代码块内，使用let声明变量之前，该变量不可用（报错// ReferenceError）
  4、不允许重复声明
### const
  1、声明只读的常量，const一旦声明必须立即初始化，常量的值不可改变
  2、不存在变量名提升
  3、暂时性死区：未声明之前，变量不可用

## 数组的解构赋值

### 基本用法
  ES6允许按照一定的模式，从数组和对象中提取值，对变量进行赋值，这被称为解构
    例：(匹配模式：只要等号两边模式相同，左边的变量就回被赋予对应的值)
      let [a, b, c] = [1, 2, 3]
      console.log(a) // 1
      console.log(b) // 2
      console.log(c) // 3

      let [foo] = []; // undefined
      let [bar, foo] = [1]; // foo等于undefined

  默认值：ES6 内部使用严格相等运算符（===），判断一个位置是否有值。所以，只有当一个数组成员严格等于undefined，默认值才会生效。
    例：
      function f() {
        console.log('aaa');
      }

      let [x = f()] = [1];
      等价于以下代码
      let x;
      if ([1][0] === undefined) {
        x = f();
      } else {
        x = [1][0];
      }

## 对象的解构赋值
## 字符串的解构赋值
## 数值和布尔值的解构赋值
## 函数参数的解构赋值

##用途
  1、交换变量的值
    let x = 1;
    let y = 2;
    [x,y] = [y,x]
  2、从函数返回多个值
  函数只能返回一个值，如果要返回多个值，只能将他们放在数组或对象里返回。
    // 返回一个数组
    function example(){
      return [1,2,3]
    };
    let [a,b,c] = example();
    // 返回一个对象
    function example(){
      return {
        foo: 1,
        bar: 2
      }
    };
    let {foo,bar} = example();

        
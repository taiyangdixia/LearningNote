# Java 8 新特性

### 一. `lambda` 表达式与`functional` 接口
1. `Lambda`表达式允许将函数作为一个方法的参数。一个简单的`Lambda`表达式可以由用逗号分隔的（参数列表）、（->符号）与（函数体）三部分表示。

        // lambda表达式示例，类似Scala
        Arrays.asList(“a”, "b", "c").forEach( e -> System.out.println(e) );

        // 加上e的参数类型写法

        Arrays.asList("a", "b", "c").forEach( (String e) -> System.out.println( e ) );

2. 函数式接口 **待进一步学习**

    `jdk8` 中所有类库中的已有接口都添加了`@FunctionalInterface` 注解。

    函数式接口首先是一个接口，这个接口里面只能有一个抽象方法。
    *函数式接口使得调用方式可以使用`lambda`表达式方式实现。*

    注意函数式接口满足以下几个条件：
  - 函数式接口中可以有default方法，必须有默认方法实现。
  - 函数式接口中可以定义静态方法，有实现。
  - 函数式接口中允许定义`java.lang.Object`中的`public`方法。
  - 函数式接口允许子接口继承多个父接口，但是每个父接口中都只能存在一个抽象方法，且必须是相同的抽象方法。，且必须是相同的抽象方法。


        // 函数式接口的注解
        @FunctionalInterface
        public interface FunctionalDefaultMethods {
          void method();
        }


`functionalInterface` 注解只是帮助进行编译级错误检查，如果写的接口不符合函数式接口定义规范，编译器就会报错。

`jdk1.8`中新增加了函数接口，`java.util.function`中包含很多类，用来支持`java`的函数式编程，该包中的函数式接口链接 [`java.util.funcition`]:http://docs.oracle.com/javase/8/docs/api/java/util/function/package-frame.html “`java.util.function Interfaces`”

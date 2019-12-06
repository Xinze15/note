# ES6正则表达式扩展
ES5的两种写法
```
let regex = new RegExp('xyz','i');
let regex2 = new RegExp(/xyz/i); 
```
ES6的写法
```
let regex = new RegExp(/xyz/ig,'i');
```
> 这样写的话后面第二个参数修饰符会覆盖前面第一个参数的修饰符。

新增的y修饰符
```
let s = 'bbb_bb_b';
let a1=/b+/g;
let a2=/b+/y;
console.log('one',a1.exec(s),a2.exec(s));//bbb bbb
console.log('two',a1.exec(s),a2.exec(s));//bb null
```
>   g 修饰符之前匹配的随意位子开始匹配，而y修饰符必须从之前匹配的下一个位子开始匹配。

新增属性sticky 判断字符串有没有开启u修饰符。

新增的u修饰符
```
console.log('u-1',/^\uD83D/.test('\uD83D\uDC2A')); //包含u代表二个字符，不包含u代表一个字符
console.log('/\u{61}/u.test('a')');//包含u unicode编码才能被js识别。
```
> unicode编码大于两个字节一定要加u才能识别。 //类似\u{20BB7}
> 正则表达中的.不是可以匹配所有的字符也是要小于两个字节的字符。




    
   

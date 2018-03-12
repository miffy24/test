js里有七种数据类型分别是number,string,boolean,null,undefined,symbol,object.
## 1.1 七种数据类型
1. number
    - 整数和小数：1 1.1 .1
    - 科学计数法：1.23e2
    - 二进制：0b11
    - 八进制：011（后来ES5添加了0o11语法）
    - 十六进制：0x11
2. string
    - 空字符串：`''`
    - 多行字符串：
        ```
        var s ='12345' +
                   '67890'  //无回车符号
        或
        var s = `12345
        67890`  //含回车符号
        ```
3. boolean

    六个false值undefined,null,false,0,NaN,""或''（空字符串）
4. symbol
5. undefined 和 null    都表示没有值
    1. （规范）如果一个变量没有被赋值，那么这个变量的值就是undefined
    2. （习俗）若想表示一个没赋值的对象就null，若是字符串/数字/布尔/symbol,就用undefined（实际var一下就行）
6. object 
    - 就是上边几种基本类型（无序的）组合在一起
    - object里面可以有object
      ```
        var person = {
            name: 'Frank', 
            'child': {
                name: 'Jack'
            }, // 最后这个逗号可有可无
        }      
      ```
    + object 的key一律是字符串，不存在其他类型的key.
    + object['']是合法的
    + object['key']可以写作object.key
    + object.key与 object[key]不同
    + delete object['key']
    + 'key' in object
## 1.2 确定值的类型的方法（3种）
- typeof运算符
    ```
    typeof 123 //"number"
    if(typeof i==="undefined"){
        //...
    }
    ```
    | 类型        | string   |  number |boolean	|symbol	|undefined	|null	|object	|function
    | -----------| -----:   | ----:  | -----:   | ----:  | -----:   | ----:  | -----:  | ----:  |
    | typeof xxx | 'string' |'number' |'boolean'|	'symbol'|	'undefined'	|'object'|	'object'|	'function'|

- instanceof运算符
    ```
    var o ={}
    o instanceof Array //false
    ```
- Object.prototype.tostring方法

```
var obj = {
    '3+3': 'A',
    '6': 'B'
}//obj[3+3] 值'B'

var name = 'x'
var obj = {
    name: 'frank'
}
//obj.name 的值为'frank'
//obj['name'] 的值'frank'
 //obj[name] 的值为undefined

# 《JS对象基本用法》
## 一、声明对象的语法
```javascript
let obj ={
    'name':'frank','xxx':'##'
}

let obj = new Object({
    'name':'frank',
    'xxx':'##'
})
console.log({
    'name':'frank',
    'xxx':'##'
})
```
* 第一种是简写语法，第二种是正规的写法,第三种是console写法。
## 二、如何删除对象的属性
语法：
```javascript
delete obj.xxx
delete obj['xxx']
```
* 不含属性名
```javascript
'xxx' in obj === false
```
* 含有属性名，但值为undefined
```javascript
'xxx' in obj && obj.xxx ===undefined
```
注意:obj.xxx === undefined
不能断定'xxx'是否为obj的属性
## 三、如何查看对象属性
  1. 查看自身所有属性： Object.keys(xxx)
  2. 查看自身+共有属性:      console.dir(xxx)
  3. 判断一个属性是自身的还是共有的：  obj.hasOwnproperty('toString')

* 查看属性两种：
 1. 中括号语法： obj['key']
 2. 点语法： obj.key
### 注意 
```javascript
obj.name等价于obj['name']
obj.name不等价于obj[name]

这里的name是字符串，而不是变量
```
``` javascript
let name = 'bai'
obj [name]等价obj['bai']
而不是obj['name']和obj.name
```
## 四、如何修改或增加对象的属性
### 1. 赋值语法：

* obj.name = 'xxx'

* obj['name'] = 'xxx'

### 2.批量赋值：
* Object.assign(obj,{
    'x':'1','xx':'2',.....
})
### 3. 改共有属性：
* Object.prototype['toString']='xxx'
### 4. 改原型：

* let obj= Object.create(common)

增加和修改基本一致，唯一的区别： 已有属性则改，没有属性则增。

## 五、'name' in obj 和obj.hasOwnproperty('name')的区别

  * obj.hasOwnproperty('name')
可以判断出是自身属性还是共有属性
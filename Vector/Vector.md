# Vec
## Vec 的创建
* 显示声明了 Vec 的类型
~~~
let v: Vec<i32> = Vec::new();
~~~
* 向里面添加一个元素后，无需显示的声明，编译器可以推倒出类型
~~~
let mut v = Vec::new();
v.push(1);
~~~
* 如果预先知道要存储的元素个数，可以创建动态数组，这样可以避免因为插入大量新数据导致频繁的内存分配和拷贝，提升性能
~~~
Vec::with_capacity(capacity);
~~~
* 使用宏 vec! 来创建数组，与 Vec::new 有所不同，宏可以在创建的同时给予初始化值
~~~
let v = vec![1, 2, 3];
~~~

## Vec 常用方法
### clear
pub fn clear(&mut self)
~~~
let mut v = vec![1, 2, 3];
v.clear();
~~~
### pop
pub fn pop(&mut self) -> Option<T>
~~~
let mut vec = vec![1, 2, 3];
assert_eq!(vec.pop(), Some(3));
~~~
### push
pub fn push(&mut self, value: T)
~~~
let mut vec = vec![1, 2];
vec.push(3);
~~~
### insert
pub fn insert(&mut self, index: usize, element: T)
~~~
let mut vec = vec![1, 2, 3];
vec.insert(1, 4);
~~~
### remove
pub fn remove(&mut self, index: usize) -> T
~~~
let mut v = vec![1, 2, 3];
assert_eq!(v.remove(1), 2);
assert_eq!(vec, [1, 4, 2, 3]);
~~~
### len
pub fn len(&self) -> usize
~~~
let a = vec![1, 2, 3];
assert_eq!(a.len(), 3);
~~~
### is_empty
pub fn is_empty(&self) -> bool
~~~
let mut v = Vec::new();
assert!(v.is_empty());
v.push(1);
assert!(!v.is_empty());
~~~

# Reference
https://doc.rust-lang.org/std/vec/struct.Vec.html

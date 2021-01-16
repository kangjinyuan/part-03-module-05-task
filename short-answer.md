### 一. 简答题

#### 1. Vue 3.0 性能提升主要是通过哪几方面体现的？

答：

- 响应式系统的升级
- 编译优化
- 源码体积的优化

#### 2. Vue 3.0 所采用的 Composition Api 与 Vue 2.x使用的Options Api 有什么区别？

答：

- Vue 2.x 中的 Options Api 包含一个描述组件选项（data，methods，components）的对象，在开发复杂组件的时候，同一功能所需要的逻辑代码被拆分到不同的选项中，逻辑代码比较混乱
- Vue 3.0 中的 Composition Api 采用函数式编程的思想，通过定义函数来实现不同的功能，不用拆分逻辑代码到不同的选项中，更灵活的组织组件逻辑

#### 3. Proxy 相对于 Object.defineProperty 有哪些优点？

答：

- 监听动态添加的属性
- 监听删除的属性
- 监听数组的索引和 length 属性

#### 4. Vue 3.0 在编译方面有哪些优化？

答：

- Vue 3.0 在编译方面，标记并提升所有的静态根节点，只会去 diff 动态节点，并且可以缓存事件处理函数，从而提高编译和代码执行的效率

#### 5. Vue.js 3.0 响应式系统的实现原理？

答：

- 通过 Proxy 对象将数据代理，在 get 中通过 track 方法收集依赖，在 set 和 deleteProperty 中通过 trigger 触发更新
- track 方法是通过 targetMap -> depsMap -> dep的存储模式，tartgetMap 存储目标对象，每一个目标对象对应自己的 depsMap，depsMap 存储目标对象的所有属性，每一个属性对应自己的 dep，dep 中存储属性的所有 effect，当触发 get 方法时，收集依赖
- trigger 方法通过 targetMap -> depsMap -> dep 的存储模式正向查找属性的 dep，遍历执行属性对应的 effect，来触发更新




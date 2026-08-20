1. 写出构造器
2. 搞定`then`方法

## 构造器
```js
class MyPromise {
    /**
     * 
     * @param {*} executor 执行器任务函数（立即执行）
     */
    constructor(executor) {
        // 数据结果
        const resolve = (data) => { };
        // 报错原因
        const reject = (error) => { };
        executor(resolve, reject);
    }
}

const p = new Promise((resolve, rejeect) => {
    let data = 1;
    resolve(data);
})
```

设置状态、结果给到对象中：
```js
class MyPromise {
    #status = 'pending';
    #result = undefined;


    /**
     * 
     * @param {*} executor 执行器任务函数（立即执行）
     */
    constructor(executor) {
        // 数据结果
        const resolve = (data) => {
            if (this.#status != 'pending') return
            this.#status = 'fulfilled';
            this.#result = data
        };
        // 报错原因
        const reject = (error) => {
            if (this.#status != 'pending') return

            this.#status = 'rejected'
            this.#result = error
        };
        executor(resolve, reject);
    }
}

const p = new Promise((resolve, reject) => {
    let data = 1;
    resolve(data);
    reject(data)
})

```

可以抽离函数、设置常量；
注意异常处理，如果抛出了异常，最好可以`reject`调用抛出错误
```js
       try {
            executor(resolve, reject);
        } catch (e) {
            reject(e)
        }
```
## 手写then方法

```js
/**
** 成功、失败后调用方法
*/
promise.then((onFulfilled,onRejected)=>{})
```
1. 回调什么时候调用
2. 返回Promise的新状态是什么

Promise已决才会选择成功/失败的函数回调。所以在调用then的时候可能不会立即实行，要等到合适的时候，无法执行怎么办，那就给他加到队列里。
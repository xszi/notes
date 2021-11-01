## Typescript

### Top level 使用await的替代方法

```js
// 这种情况会报错，因为Top level 使用await属于较新的语法，某些环境不支持
for (const path in modules) {
    let mod: mod = await modules[path]();
    console.log(mod);
    // 数据添加到routes中
    routes.push(...mod.default)
}
```

```js
// 将上面方法进行改写
for (const path in modules) {
    let mod: any = '';
    async function main(): Promise<void> {
        mod = await modules[path]()
    }
    main();
    console.log(mod);
    // 数据添加到routes中
    routes.push(...mod.default)
}
```
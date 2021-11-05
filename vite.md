vite打包vue3项目
```js
// vite.config.ts
import vue from '@vitejs/plugin-vue'
import vueJsx from "@vitejs/plugin-vue-jsx"
// 是babel-plugin-import的vite版本轮子
import vitePluginBabelImport from 'vite-plugin-babel-import'

export default defineConfig({
    server: {},
    plugins: [vue(),
        vueJsx(),
        // 使用该插件可以达到按需加载的效果， 不需要在main.js中全部引入
        vitePluginBabelImport([
            {
                libraryName: 'element-plus',
                libraryDirectory: 'es',
                style(name) {
                    return `element-plus/lib/theme-chalk/${name}.css`;
                }
            }
        ])
    ]
})
```
```js
<!-- xxx.vue -->
<script lang="ts" setup>
import { ElMessage } from 'element-plus'
ElMessage.error("🙅‍♀️用户名密码不能为空")
</script>
```
# 写博客
* 在source\_posts目录下新建你的文章
* 文章的格式为.md

# 预览博客

## 环境确认
暂略

## 启动预览
``` sh
# 会看到本地预览地址：http://localhost:4000
> npm run server
```
在浏览器中打开预览网站即可预览文章效果。如果页面没有更新，停止预览窗口并重新运行上面的预览命令即可


# 更新博客
文章写好后，运行以下命令
```
# 编译博客
npm run build

# 重命名文件public 为 doc(github pages 要求)
ren "public" "doc"

# 提交更改
git add .
git commit '更新博客'
git push
```
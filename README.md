## 一、基础配置
### 1.1、本地安装 hexo
```
npm i -g hexo
```

### 1.2、项目初始化
```
hexo init
```

### 1.3、目录说明
```
node_modules：是依赖包
public：存放的是生成的页面
scaffolds：命令生成文章等的模板
source：用命令创建的各种文章
themes：主题
_config.yml：整个博客的配置
db.json：source解析所得到的
package.json：项目所需模块项目的配置信息
```

### 1.4、本地运行
- `npm i hexo-server`
- 然后运行 `hexo server`

### 1.5、github配置
- 创建一个repository，名称为`yourname.github.io`, 其中yourname是你的github名称，按照这个规则创建github page才会生效
- 修改 `_config.yml` 中的git配置

```
deploy:
  type: git
  repo:  https://github.com/xxxx.git
  branch: master
```

### 1.6、部署上传
- 在本地安装上传工具

```
npm install hexo-deployer-git --save
```

- 依次执行如下命令

```
hexo clean      // 删除上次打包
hexo generate   // 打包
hexo deploy     // 上传
```

在浏览器中输入 `http://yourgithubname.github.io` 就可以看到你的个人博客了！

### 1.7、一些其他配置
#### 搜索功能
```
npm install -S hexo-generator-json-content
```
然后

```
search:
    insight: true
```

#### readme
- 首先在source文件夹下建立一个 `README.md`
- 修改 `_config.yml`

```
skip_render: README.md
```

## 二、绑定个人域名
### 2.1、购买一个域名
### 2.2、域名解析
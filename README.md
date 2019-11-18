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
- 进入控制台添加域名解析
- 按照如下规则添加两条纪录
![]('./1.png')

- 这时去访问解析好的域名会出现如下页面，这说明域名解析没有问题，接下来进入github进行配置
![]('./2.png')

### 2.3、hexo 配置
- 在本地的博客目录中找到source文件夹。
- 新建一个没有后缀名的文件 CNAME
- 在文件中添加你的域名，如 `xichaoming.top`
- 保存后重新生成，并提交你的博客

### 2.4、github 配置
- 在github中找到你的博客仓库。
- 点击 `Setting`
- 找到 `Custom domain`
- 输入你的域名点击save
- 然后你就可以在浏览器用你的域名愉快的访问啦

## 三、同时托管到 github 和 coding
> github page毕竟是国外站点，访问速度相对来说比较慢，但是同时你又想在gihub上保存一下代码，可以尝试同时托管两个仓库。
>
> 做解析的时候海外的ip 指向到github，国内的或者说百度的直接指向coding。
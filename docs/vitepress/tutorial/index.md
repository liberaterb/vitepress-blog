## vuepress demo搭建

### 搭建顺序

1. 安装依赖
   ~~~ powershell
   npm init -y
   npm i -D vuepress
   ~~~

2. 添加 scripts
    ~~~ json
    "scripts": {
        "docs:dev": "vuepress dev docs",
        "docs:build": "vuepress build docs"
    }
    ~~~

3. 创建文件目录

    ~~~powershell
    mkdir dist
    mkdir docs
    # 创建首页介绍文档
    echo '# Hello VuePress' > docs/README.md
    mkdir docs/.vuepress
    # 创建配置文件
    New-Item docs/.vuepress/config.js
    # 创建demo文档
    echo '## vuepress demo搭建' > docs/vuepress/tutorial/README.md
    ~~~

4. 编辑配置文件

    ~~~javascript
    module.exports = {
        title: 'daily note',
        dest: './dist',
        themeConfig: {
            nav: [{
                text: 'vitepress', link: '/vitepress/',
                items: [
                    { text: 'demo搭建', link: '/vitepress/tutorial/' }
                ]
            }],
            sidebar: 'auto'
        }
    }
    ~~~

    
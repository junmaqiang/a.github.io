# 抗衰主题站点

欢迎访问【抗衰】主题站点。

## 🚀 使用步骤

1. 解析域名：
    ```text
    # 先让域名解析成功，产生 CNAME 文件
    ```

2. 克隆仓库:
    ```bash
    git clone git@github.com:junmaqiang/a.github.io.git
    ```

3. 初始化 chglog:
    ```bash
    # a. 执行命令
    git-chglog --init
   
    # b. 交互信息
    #? What is the URL of your repository? https://github.com/junmaqiang/a.github.io
    #? What is your favorite style? github
    #? Choose the format of your favorite commit message <type>: <subject>
    #? What is your favorite template style? standard
    #? Do you include Merge Commit in CHANGELOG? Yes
    #? Do you include Revert Commit in CHANGELOG? Yes
    #? In which directory do you output configuration files and templates? .chglog
    #✨  Configuration file and template generation completed!
    #✔ .chglog/config.yml
    #✔ .chglog/CHANGELOG.tpl.md
    
   # c. 产出文件
    # 这会生成 .chglog/config.yml 和 .chglog/CHANGELOG.tpl.md 文件
    #
    ```

4. 配置文件:
    ```bash
    .gsemver.yaml 文件放到项目根目录
    ```

5. 配置hook钩子:
    ```bash
    tee .git/hooks/pre-commit <<EOF
    #!/bin/sh
    /Users/jun/docker/go/gopath/bin/git-chglog -output CHANGELOG.md
    exit 0;
    EOF
    ```

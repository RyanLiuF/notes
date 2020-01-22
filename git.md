### 代理配置
    + git config --global http.proxy proxyhk.zte.com.cn:80
    + 撤销代理：git config --global --unset http.proxy
### 版本回退
    + 撤销上次提交，本地代码不删除：git reset --soft HEAD^
    + 撤销上次提交，本地代码删除：git reset --hard HEAD^

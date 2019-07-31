 - gitignore规则不生效的解决办法
 
```
把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，
原因是.gitignore只能忽略那些原来没有被追踪的文件，
如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。
那么解决方法就是先把本地缓存删除（改变成未被追踪状态），然后再提交：
```

```
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```
```
其中-r是删除文件夹及其子目录
--cached是删除暂存区里的文件而不删除工作区里的文件，
```
##### 查看git下的文件 
 ```git ls-files```
##### 添加远程仓库
 ```
$ git remote  
    origin  

$ git remote add pb https://github.com/paulboone/ticgit

$ git remote -v
pb      https://github.com/bruceyangjie/java-code-bundles.git (fetch)
pb      https://github.com/bruceyangjie/java-code-bundles.git (push)

```

…or create a new repository on the command line

``` 
    echo "# java-code-bundles" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin git@github.com:bruceyangjie/java-code-bundles.git
    git push -u origin master
```
…or push an existing repository from the command line
```
   git remote add origin git@github.com:bruceyangjie/java-code-bundles.git
   git push -u origin master
```
> 常见的文件管理命令  
>> mkdir name 创建一个目录   
>> pwd 显示当前目录   
>> git init 将这个目录变成git可以管理的目录；创建成功后可以看到目录下有一个.git文件夹，是git 用于跟踪版本库的  
>> git add file 将name目录下的文件提交到git  
>> git commit -m "..."告诉git把文件提交到仓库  
>> git status查看状态  
>> git diff file查看改动情况  
>> git log查看日志  
>> git checkout file 回到最近一次git add 或git commit的状态  
>> rm file删除文件

> GitHub远程仓库同步本地仓库  
>> ssh-keygen -t rsa -C"****@qq.com**" 建立连接  
>> GitHub中Create a new repo  
>> 将本地的仓库和GitHub中新建仓库同步  
>>> git remote add origin git@github.com:wang-ting000/learngit.git    
>>> git push -u origin master  


> 从GitHub克隆仓库  
>> git clone git@github.com:wang-ting000/gitskills.git  


> 分支  
>> 作用：创建分支存储工作，而且主线不会被影响，直到提交才会显示到master  
>> git checkout -b dev创建并切换到dev分支  
>> git branch查看当前分支  
>> git checkout master切换回master分支  
>> git merge dev 合并指定分支到当前分支
>> git branch -d dev删除分支  


> 标签  
>> git checkout master 切换到需要打标签的分支
>> git tag v1.0打标签啊  
>> git tag 查看所有标签  
>> git tag -d v0.1删除标签  
>> git push origin --tags把标签推送到远程  
>> git tag -d v0.9；git push origin :refs/tags/v0.9删除远程标签  

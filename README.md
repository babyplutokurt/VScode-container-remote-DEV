# VScode-container-remote-DEV
ALL [] in this file: 需要自行更改
1. 将本机.ssh文件夹中的公钥复制到远程主机~/.ssh/authorized_keys文件中
   
   ssh-copy-id -i ~/.ssh/id_rsa.pub [user]@[server]
   
   Example: ssh-copy-id -i ~/.ssh/id_rsa.pub babypluto@192.168.0.1
   
2. 打开终端输入命令ssh [用户名]@[主机IP]，若能无密码访问，则继续下一步

3. 打开VSCode，安装插件Remote Development

4. 配置docker context，使用docker context命令
   docker context create [ContextName_XXX] --docker "host=ssh://username@hostname"
   
  其他命令： docker context rm [name]
             
             docker context use [name]
             
             docker context ls 显示所有context
             
5. 新建文件夹，在该文件夹中新建.vscode文件夹，新建文件./vscode/settings.json, 插入配置语句："docker.host": "ssh://[用户名]@[主机IP]"

6. 使用VSCode打开文件夹

7. 打开VSCode远程资源管理器，选择Containers，等待显示出远程主机上运行的容器

8. 右键点击容器，选择Attach to Container
 ![image](https://user-images.githubusercontent.com/67892316/147260094-1a489cc8-39a4-44d8-8d03-dd9286335140.png)








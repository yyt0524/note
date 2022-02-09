将本地文件夹（项目）上传到GitHub
1 新建文件夹
2 git clone
3 cd 到clone的目录中
4 将文件夹（目录）复制到目录中
5 进行提交git commit -m '信息'
6 推送git push
注：在执行第六步时会发生错误：
fatal: An error occurred while sending the request.
fatal: The request was aborted: Could not create SSL/TLS secure channel.
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
该错误提示我们需要在GitHub创建对应的key
1 登录GitHub账号
2 账户设置选择SSH and GPG keys，并按照提示在命令行生成key，在本地administrator目录找到key，添加到SSH key
3 账户设置选择Developer settings->Personal access tokens生成token，并复制该token
4 进入本机之前的clone的目录，编辑config文件，将token添加到URL中，格式为：url=https://你的token@你的项目git网络地址
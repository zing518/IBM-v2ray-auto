# IBM-v2ray-auto
利用IBM，快速创建v2ray，且内置自动定时重启功能

食用方法：
~~~
#非必须步骤，脚本运行后可能会提示更新pip之类的，但是不影响跑脚本，如果看着不舒服，执行如下指令
python --version  //查看一下Python的版本
若是Python2.x，
python -m pip install --upgrade pip
若是Python3.x，
python3 -m pip install --upgrade pip  

# 一键搭建脚本
wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/gouidea/IBM-v2ray-auto/master/install.sh && chmod +x install.sh  && ./install.sh


# 安装步骤
用户名称—>个人邮箱
用户密码—>密码
# 输入后会自动登录到IBM cloud，账户正确则提示授权OK，如果未成功登陆，Ctrl + c取消安装，重新运行代码安装
应用名称—>容器应用名
应用环境—>1或者2  1——伪装go,2——伪装python
# 应用环境自己随便选都可以，都是无用的示例代码，仅用作伪装
伪装文件名称—>自行命名（尽量全英文）
内存—>256
# 然后会自动push到容器，生成的vmess代码可以直接使用


# 验证是否安装成功方法
直接复制vmess链接到客户端，看能否访问谷歌
~~~

cf反代域名加速
~~~
addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="待加速的地址";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  })
~~~

参考项目：

https://github.com/w2r/IBMYesPLus

https://github.com/CCChieh/IBMYes

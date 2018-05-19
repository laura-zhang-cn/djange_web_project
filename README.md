# djange_web_project


## 1. 安装与配置
pip install django

environment path  :  your-python-lib-path\site-packages\django\bin


## 2. 第一步：创建一个工程，并成功启动它（本地可在浏览器访问）  
命令行运行：  
> cd  一个自定义的工程路径/     #such as  cd E:\djtest  
> E:\djtest>  django-admin startproject  first_test  
> E:\djtest>  cd first_test  
> E:\djtest\first_test >  python manage.py runserver 0.0.0.0:8000    # keep on-line ,don’t quit   

浏览器打开：  
http://127.0.0.1:8000/   # remind some words such as   ".....work succefully..."   "it worked ...."  


## 3. 第二部：建立视图文件，刷新访问网址时，覆盖之前默认的显示内容    
工程目录E:\djtest\first_test\first_test\下：  
新建 view.py  编辑内容：  

    ----------------
    from django.http import HttpResponse
    
    def ftest(request):
        return HttpResponse('first test zyx')
    
    def hpage(request):
        return HttpResponse('home page zyx')
    
    #这里自定义了两个，为了对比访问不同页面路径的内容显示差异
    ----------------
    
打开 urls.py ，覆盖内容，也可以不覆盖，采用新增（但没成功，所以还是覆盖了..)：

    ----------------  
    from django.conf.urls import url  
    from . import view  
    
    # url第一个参数pattern是匹配的网址的路径 ,第二个参数是要调用的函数  
    urlpatterns=[   
            url(r'^first$',view.ftest),     # 访问 127.0.0.1:8000/first 页面显示ftest的内容
            url(r'^$',view.hpage)     # 访问 127.0.0.1:8000/  页面显示hpage的内容
    ]   
    ----------------  
    

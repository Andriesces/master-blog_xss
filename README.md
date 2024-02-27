# master-blog_xss
master-blog_xss  
system url:https://gitee.com/manster1231/master-blog  
A vulnerability was found in master-blog system . The manipulation of the argument description with the input <script>alert(document.cookie)</script> leads to cross site scripting. It is possible to initiate the attack remotely.  
Click the add article button, write a malicious script in the content of the public article, and then click "publish".  
![image](https://github.com/Andriesces/master-blog_xss/assets/139127885/7e0afe42-ecd8-4018-ac03-e97a8634e5ed)  
![image](https://github.com/Andriesces/master-blog_xss/assets/139127885/b37d3051-22a7-4ac6-9516-58ee343e7705)



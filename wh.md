JFinalCMS system has an arbitrary file read security problem

**Project Address**  
https://gitee.com/heyewei/JFinalcms

**Project Issues**  
https://gitee.com/heyewei/JFinalcms/issues/IAOSJG

**This interface has an arbitrary file writing capability (path controllable)**  
/admin/template/edit

com.cms.controller.admin.TemplateController#edit method accepts the parameters passed in (file name)  
![](https://github.com/xingjiuW/cve/blob/main/images/%E5%9B%BE%E7%89%871.png)
com.cms.util.TemplateUtils#read. The utility class (FileUtils) in Apache Commons IO is then called to implement the file reading function  
![](https://github.com/xingjiuW/cve/blob/main/images/%E5%9B%BE%E7%89%872.png)  
Construct a request package  
![](https://github.com/xingjiuW/cve/blob/main/images/%E5%9B%BE%E7%89%873.png)
The system file is read successfully (the /etc/passwd file is used as an example).  
![](https://github.com/xingjiuW/cve/blob/main/images/%E5%9B%BE%E7%89%874.png)

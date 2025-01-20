### Medidata Business Object 4.2 with deep link directly to EDC datapage(logline)

进入BO4模块,新建一个web intelligence，在Query Panel 的Universe outline的左侧栏找到RaveX Deep Link Objects
![image](https://github.com/user-attachments/assets/a51bbc3c-d8d6-4b4a-ba09-22dee34a65e6)
选中RaveX Deep Link Objects下的四个参数，并分别选择Subject Id, Data Page ID和Log#放至Result Objects。点击右上角的Run Query:
![1737355058269](https://github.com/user-attachments/assets/995b7110-d742-4dc4-8b5c-a9b5588af37c)

弹窗Query Contexts选择Data：

![image](https://github.com/user-attachments/assets/c6814982-98e6-4732-a306-7091bd480e7e)

运行完后在左侧Variable处右击选择New，新建变量：

![image](https://github.com/user-attachments/assets/8f0a2430-39c6-4d79-ae21-c0f8091a8742)

填写变量的Name，Description和Formula: 

![image](https://github.com/user-attachments/assets/a42b7929-c1bf-40e7-a671-733d3a2d74e6)

将新建的Link变量拖动至报表中：

![image](https://github.com/user-attachments/assets/8f30486c-4e72-4253-a4a4-288c9f6329c0)

选中Deep link，右击添加超链接：

![image](https://github.com/user-attachments/assets/00f736f7-99c3-4e74-9dca-dd419f9594ad)

粘贴以下文本后点击Parse。以下文本源自URL向Medidata服务器发送请求时的结构，服务器返回的结果处理后即可变成我们看到的EDC前台界面。可以通过点击进入任意受试者的某个Logline页面来观察。（非logline页面可通过recordNumber=0访问）:

https://mcc.imedidata.com/apps/edc/index/" + [StudySiteUUID] + "?c_selections=(="com:mdsol:actions:spa_index,com:mdsol:client_division_schemes:" + [ClientDivisionSchemeUUID] + ",com:mdsol:studies:" + [StudyUUID] + ",com:mdsol:study_environments:" + [StudyEnvUUID] + "#!/subject/" + [Subject Id] + "/datapage/" + [Data Page ID] + "?recordNumber=" + [Log #])

![image](https://github.com/user-attachments/assets/9929b0a6-5953-48c4-9d9a-9a643052bb48)

![image](https://github.com/user-attachments/assets/1a6f6a4c-214f-4f6a-8ec2-210443787471)

最后删除f(x)栏中的URLEncode后保存：

![image](https://github.com/user-attachments/assets/75e2d29f-4a04-4951-a1f7-89e10d34c92d)

最终导出的报告中（如为.xlsx格式），最后一列为超链接，可点击直达Rave EDC对应的受试者页面（需提前登录Rave EDC系统）。

参考资料：
[BO_4.1_PublishingReportstoRave_ENG_v1.0_Final (1).pdf](https://github.com/user-attachments/files/18473358/BO_4.1_PublishingReportstoRave_ENG_v1.0_Final.1.pdf)
[Uploading BO_4.2_SAP_函数公式计算.pdf…]()
[Uploading BO4 user_guide_en.pdf…]()

 

---
title: 取消excel工作薄密码保护方法
date: 2012-10-30 14:21:15
tags: CSDN迁移
---
   1、打开任一excel文件

 2、在宏里粘贴下面的代码

 3、运行下面的代码

 4、选择需要破解密码的文件

 5、点击“打开”

 

 '移除VBA编码保护  
 Sub MoveProtect()  
 Dim FileName As String  
 FileName = Application.GetOpenFilename("Excel文件（*.xls & *.xla&*.xlsx）,*.xls;*.xla;*.xlsx", , "VBA破解")  
 If FileName = CStr(False) Then  
 Exit Sub  
 Else  
 VBAPassword FileName, False  
 End If  
 End Sub

 '设置VBA编码保护  
 Sub SetProtect()  
 Dim FileName As String  
 FileName = Application.GetOpenFilename("Excel文件（*.xls & *.xla&*.xlsx）,*.xls;*.xla;*.xlsx", , "VBA破解")  
 If FileName = CStr(False) Then  
 Exit Sub  
 Else  
 VBAPassword FileName, True  
 End If  
 End Sub

 Private Function VBAPassword(FileName As String, Optional Protect As Boolean = False)  
 If Dir(FileName) = "" Then  
 Exit Function  
 Else  
 FileCopy FileName, FileName & ".bak"  
 End If

 Dim GetData As String * 5  
 Open FileName For Binary As #1  
 Dim CMGs As Long  
 Dim DPBo As Long  
 For i = 1 To LOF(1)  
 Get #1, i, GetData  
 If GetData = "CMG=""" Then CMGs = i  
 If GetData = "[Host" Then DPBo = i - 2: Exit For  
 Next  
   
 If CMGs = 0 Then  
 MsgBox "请先对VBA编码设置一个保护密码...", 32, "提示"  
 Exit Function  
 End If  
   
 If Protect = False Then  
 Dim St As String * 2  
 Dim s20 As String * 1  
   
 '取得一个0D0A十六进制字串  
 Get #1, CMGs - 2, St  
   
 '取得一个20十六制字串  
 Get #1, DPBo + 16, s20  
   
 '替换加密部份机码  
 For i = CMGs To DPBo Step 2  
 Put #1, i, St  
 Next  
   
 '加入不配对符号  
 If (DPBo - CMGs) Mod 2 <> 0 Then  
 Put #1, DPBo + 1, s20  
 End If  
 MsgBox "文件解密成功......", 32, "提示"  
 Else  
 Dim MMs As String * 5  
 MMs = "DPB="""  
 Put #1, CMGs, MMs  
 MsgBox "对文件特殊加密成功......", 32, "提示"  
 End If  
 Close #1  
 End Function

   
   
 
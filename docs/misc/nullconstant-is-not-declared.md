---
title: "&#39;&lt;nullconstant&gt;&#39;가 선언되지 않았습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30822"
  - "vbc30822"
helpviewer_keywords: 
  - "BC30822"
ms.assetid: dda0e2c1-46a3-4cc4-b36c-0858a5259bac
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nullconstant&gt;&#39;가 선언되지 않았습니다.
'\<nullconstant\>'가 선언되지 않았습니다. 'Null' 상수가 더 이상 지원되지 않으므로 대신 System.DBNull을 사용하세요.  
  
 문이 Visual Basic에서 더 이상 지원되지 않는 `Null` 키워드를 사용합니다.  
  
 **오류 ID:** BC30822  
  
### 이 오류를 해결하려면  
  
1.  <xref:System.DBNull> 대신 `Null`를 사용합니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Sub TestDBNull() Dim t As DataTable ' Assume the DataGrid is bound to a DataTable. t = CType(DataGrid1.DataSource, DataTable) Dim r As DataRow r = t.Rows(datagrid1.CurrentCell.RowNumber) r.BeginEdit r(1) = System.DBNull.Value ' Assign DBNull to the record. r.EndEdit r.AcceptChanges If r.IsNull(1) Then MsgBox("") End If End Sub  
    ```  
  
2.  개체 변수를 사용하는 경우 할당 및 비교에 대해 [Nothing](/dotnet/visual-basic/language-reference/nothing) 키워드를 사용합니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Sub TestNothing() Dim cls As Object ' cls is Nothing if it has not been assigned using the New keyword. If (cls Is Nothing) Then MsgBox("cls is Nothing") End If cls = Nothing ' Assign Nothing to the class variable cls. End Sub  
    ```  
  
## 참고 항목  
 <xref:System.DBNull>   
 [Nothing](/dotnet/visual-basic/language-reference/nothing)   
 [Programming Element Support Changes Summary](http://msdn.microsoft.com/ko-kr/0483590a-6309-449c-a2fa-effa26a03b95)
---
title: "예외 문제 해결: System.Data.NoNullAllowedException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "NoNullAllowedException 클래스"
ms.assetid: 1ab87572-007f-4b84-bb13-c3626e7f89cd
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.NoNullAllowedException
<xref:System.Data.NoNullAllowedException> 예외는 <xref:System.Data.DataColumn.AllowDBNull%2A>이 `false`로 설정된 열에 null 값을 삽입하려는 경우에 throw됩니다.  
  
## 관련 팁  
 **값을 열에 추가하기 전에 값이 DBNull인지 확인하십시오.**  
 <xref:System.Data.DataColumn.AllowDBNull%2A>이 `false`로 설정되어 있으면 null 값을 삽입할 수 없습니다. 자세한 내용은 <xref:System.DBNull>을 참조하십시오.  
  
 **AllowDBNull을 True로 설정하십시오.**  
 이 속성을 `true`로 설정하면 null 값을 삽입할 수 있습니다. 자세한 내용은 <xref:System.Data.DataColumn.AllowDBNull%2A>을 참조하십시오.  
  
## 설명  
 데이터 폼에서 탐색 단추를 사용하여 데이터베이스 테이블의 레코드 간에 이동하는 경우 "'Column' 열에 null을 사용할 수 없습니다."라는 추가 정보와 함께 이 예외가 throw될 수 있습니다. 이 동작은 데이터 폼 마법사에서 데이터베이스 테이블의 "NULL이 아님" 열이나 기본 키를 선택하지 않았기 때문에 발생합니다. 데이터 폼을 만들 때 데이터 폼 마법사에서 데이터베이스의 "NULL이 아님" 열이나 기본 키를 선택하지 않으면 **추가 \- 새 레코드를 만듭니다.** 옵션이 비활성화되지 않습니다. 이 문제를 해결하려면 데이터 폼 마법사를 사용하여 데이터 폼을 추가할 때 선택된 테이블에서 NULL이 허용되지 않는 열과 기본 열을 선택합니다.  
  
## 참고 항목  
 <xref:System.Data.NoNullAllowedException>   
 <xref:System.Data.DataRowCollection.Add%2A>   
 <xref:System.Data.DataRow.EndEdit%2A>   
 <xref:System.Data.DataRow.ItemArray%2A>   
 <xref:System.Data.DataTable.LoadDataRow%2A>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
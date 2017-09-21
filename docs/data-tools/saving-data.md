---
title: "데이터 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataRow.RowState"
  - "DataSet.GetChanges"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 저장"
  - "데이터[Visual Studio], 업데이트"
  - "데이터베이스, 업데이트"
  - "DBDirect 메서드"
  - "데이터 저장"
  - "TableAdapter DBDirect 메서드"
  - "TableAdapter.Update 메서드"
  - "데이터 업데이트"
  - "데이터베이스 업데이트"
ms.assetid: 21d2b115-62e4-4ac9-a873-dcbb535b8af8
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 데이터 저장
데이터 저장은 응용 프로그램의 데이터 모델에서 변경된 데이터를 원래 데이터 저장소\(일반적으로 SQL Server와 같은 관계형 데이터베이스\)에서 유지할 수 있도록 하는 프로세스입니다.  
  
 데이터 모델을 통해 데이터 소스를 업데이트하는 과정은 일반적으로 두 단계로 진행됩니다.  첫째 단계는 새 레코드, 변경된 레코드, 삭제된 레코드와 같은 새 정보로 데이터 모델을 업데이트하는 것입니다.  둘째 단계는 데이터 모델의 변경 사항을 데이터베이스에 다시 저장하는 것입니다.  
  
 다음 항목에서는 데이터 저장과 관련된 개념 및 작업을 설명합니다.  
  
## 관련 항목  
 [데이터 집합에 데이터 저장](../data-tools/save-data-back-to-the-database.md)  
 데이터 집합을 변경하는 방법과 변경 내용을 데이터베이스에 저장하기 위해 데이터 집합에서 변경 사항에 대한 정보를 추적하는 방법을 간략하게 설명합니다.  
  
 [엔터티 데이터 저장](../data-tools/saving-entity-data.md)  
 [ADO.NET Entity Framework](../Topic/ADO.NET%20Entity%20Framework.md) 및 [WCF Data Services 4.5](../Topic/WCF%20Data%20Services%204.5.md) 응용 프로그램에서 변경 내용을 저장하는 방법에 대해 설명합니다.
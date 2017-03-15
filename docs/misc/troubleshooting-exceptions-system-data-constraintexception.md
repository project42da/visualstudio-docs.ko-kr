---
title: "예외 문제 해결: System.Data.ConstraintException | Microsoft Docs"
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
  - "ConstraintException 클래스"
ms.assetid: 5e9ba3b8-73d5-4657-a76e-63ab6ea32cf1
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.ConstraintException
<xref:System.Data.ConstraintException> 예외는 제약 조건을 위반하는 작업을 시도하는 경우에 throw됩니다.  
  
## 관련 팁  
 **데이터 집합에서 제약 조건을 완화하거나 해제하십시오.**  
 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성을 사용하면 <xref:System.Data.DataSet> 개체의 테이블을 채우는 동안 제약 조건을 임시로 해제할 수 있습니다.  
  
 **기본 키가 이미 데이터 테이블에 있는 기본 키 필드에 값을 할당하지 않도록 하십시오.**  
 기본 키가 있는 경우 이 예외가 throw됩니다.  
  
 **뷰 상태에서 로드하기 전에 데이터 집합을 지우십시오.**  
 데이터 집합을 로드할 때 데이터 집합에 데이터가 있으면 이 예외가 throw될 수 있습니다.  
  
## 참고 항목  
 <xref:System.Data.ConstraintException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
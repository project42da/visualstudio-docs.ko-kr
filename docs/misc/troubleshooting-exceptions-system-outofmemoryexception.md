---
title: "예외 문제 해결: System.OutOfMemoryException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
  - "OutOfMemoryException 클래스"
ms.assetid: eb16f008-964e-40a1-91f6-6ad25fa82d5a
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.OutOfMemoryException
<xref:System.OutOfMemoryException> 예외는 메모리 할당에 실패한 경우에 throw됩니다.  
  
## 관련 팁  
 **배열을 만드는 경우 크기가 올바른지 확인하세요.**  
 Visual Basic에 관련된 자세한 내용은 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)을 참조하세요.  
  
 C\#에 관련된 자세한 내용은 [배열](/dotnet/csharp/programming-guide/arrays/index)을 참조하세요.  
  
 **내부 용도 및 관리되는 새 개체를 위해 할당할 수 있는 메모리가 충분한지 확인하세요.**  
 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]에서 프로그래밍하는 경우 공용 언어 런타임은 내부용이나 새로운 관리되는 개체에 대해 메모리가 충분하지 않은 경우 이 예외를 throw합니다. 이 예외가 발생하지 않도록 하려면 64KB 이상의 메모리를 사용하는 큰 메서드를 가능하면 프로그래밍하지 않아야 합니다.  
  
## 설명  
 일반적으로 다음과 같은 경우에 관리되는 메모리 사용량이 크게 증가합니다.  
  
-   큰 데이터 집합을 메모리에 읽어들이는 경우  
  
-   과도한 캐시 엔트리를 만드는 경우  
  
-   큰 파일을 업로드하거나 다운로드하는 경우  
  
-   파일을 구문 분석할 때 정규식이나 문자열을 지나치게 많이 사용하는 경우  
  
-   과도한 뷰 상태인 경우  
  
-   세션 상태에 데이터가 너무 많거나 세션이 너무 많은 경우  
  
 안전 배열\(크기가 고정되지 않는 배열\)이 포함된 사용자 정의 형식을 반환하는 COM 개체에 대해 메서드를 호출하는 경우 이 예외는 "사용 가능한 저장소가 부족하여 이 작업을 완료할 수 없습니다"라는 추가 메시지와 함께 throw될 수 있습니다. .NET Framework에서 안전 배열 형식의 구조체 필드를 마샬링할 수 없기 때문입니다.  
  
## 참고 항목  
 <xref:System.OutOfMemoryException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
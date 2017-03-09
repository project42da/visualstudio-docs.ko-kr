---
title: "예외 문제 해결: System.StackOverflowException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "StackOverflowException 클래스"
ms.assetid: 51b71217-c507-4f5b-bc35-0236180d7968
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.StackOverflowException
<xref:System.StackOverflowException> 예외는 메서드 호출이 너무 많이 중첩되어 실행 스택이 오버플로하는 경우에 throw됩니다.  
  
## 관련 팁  
 무한 루프 또는 무한 재귀가 없는지 확인하십시오.  
 메서드 호출이 너무 많은 경우 이는 대부분 너무 깊거나 종료 조건이 없는 재귀를 의미합니다.  
  
## 설명  
 예외 처리 코드에는 스택이 필요할 수 있으므로 스택 오버플로 예외는 catch할 수 없습니다. 대신, 일반적인 응용 프로그램에서 스택 오버플로가 발생하면 CLR\(공용 언어 런타임\)에서 프로세스를 종료합니다.  
  
 CLR을 호스팅하는 응용 프로그램에서는 기본 동작을 변경하여 CLR에서 예외가 발생한 응응 프로그램 도메인을 언로드하고 프로세스를 계속하도록 지정할 수 있습니다. 자세한 내용은 [ICLRPolicyManager 인터페이스](../Topic/ICLRPolicyManager%20Interface.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.StackOverflowException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Loop Structures](/dotnet/visual-basic/programming-guide/language-features/control-flow/loop-structures)
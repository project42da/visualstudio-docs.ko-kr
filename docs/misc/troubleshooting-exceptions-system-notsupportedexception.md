---
title: "예외 문제 해결: System.NotSupportedException | Microsoft Docs"
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
  - "NotSupportedException 클래스"
ms.assetid: a214e851-ee0f-4bbd-9f72-8769046526f3
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.NotSupportedException
<xref:System.NotSupportedException> 예외는 호출한 메서드가 지원되지 않는 경우 또는 호출한 기능을 지원하지 않는 스트림에 대해 읽기, 찾기 또는 쓰기 작업을 수행하려는 경우에 throw됩니다.  
  
## 관련 팁  
 **메서드가 지원되는지 확인하십시오.**  
 기본 클래스에서 지원되지 않는 메서드가 있습니다. 이러한 메서드는 파생 클래스에서 대신 지원됩니다. 기본 클래스의 메서드에 대한 하위 집합만 파생 클래스에서 구현하는 경우 지원되지 않는 메서드에 대한 <xref:System.NotSupportedException> 예외가 throw됩니다.  
  
## 설명  
 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]로 작업하면서 네이티브 함수에 대해 P\/Invoke를 사용할 때 다음과 같은 상황에서 이 예외가 throw될 수 있습니다.  
  
-   관리 코드의 선언이 올바르지 않은 경우  
  
-   수행하려는 작업을 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]에서 지원하지 않는 경우  
  
-   내보내기 과정에서 DLL 이름이 손상된 경우  
  
-   이러한 경우에는 다음을 확인합니다.  
  
-   [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] P\/Invoke 제한 사항에 대한 위반 여부  
  
-   메모리를 미리 할당해야 하는 인수가 있는지 여부. 이러한 인수가 있으면 기존 변수에 대한 참조를 전달해야 합니다.  
  
-   내보낸 함수의 이름이 올바른지 여부. 이는 DumpBin.exe를 사용하여 확인할 수 있습니다.  
  
-   너무 많은 인수를 전달하려 하지 않았는지 여부  
  
## 참고 항목  
 <xref:System.NotSupportedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
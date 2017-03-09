---
title: "예외 문제 해결: System.IO.InternalBufferOverflowException | Microsoft Docs"
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
  - "InternalBufferOverflowException 클래스"
ms.assetid: 1f58ca15-c4e4-4af9-9a3d-42d2cf919cbe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IO.InternalBufferOverflowException
<xref:System.IO.InternalBufferOverflowException> 예외는 내부 버퍼 오버플로가 발생한 경우에 throw됩니다.  
  
## 관련 팁  
 **FileSystemWatcher를 사용하는 경우 원하지 않는 변경 알림은 필터를 사용해 제외시키십시오.**  
 파일 시스템 감시자에서 파일 변경 내용이 통보되면 구성 요소가 만들어 API\(응용 프로그래밍 인터페이스\)에 전달하는 버퍼에 이러한 변경 내용이 저장됩니다. 짧은 시간 동안 많은 사항이 변경되면 버퍼가 오버플로할 수 있고 그 결과로 <xref:System.IO.InternalBufferOverflowException> 예외가 발생하여 변경 내용이 모두 소실될 수 있습니다. 버퍼의 오버플로를 방지하려면 <xref:System.IO.FileSystemWatcher.NotifyFilter%2A> 및 <xref:System.IO.FileSystemWatcher.IncludeSubdirectories%2A> 속성을 사용하여 불필요한 변경 알림을 필터링하여 제거합니다. 자세한 내용은 <xref:System.IO.FileSystemWatcher>을 참조하십시오.  
  
## 설명  
 <xref:System.IO.FileSystemWatcher.InternalBufferSize%2A> 속성을 통해 내부 버퍼의 크기를 늘릴 수도 있습니다. 그러나 버퍼의 크기를 늘리면 성능이 저하될 수 있으므로 버퍼는 가능한 한 작게 유지하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.IO.InternalBufferOverflowException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
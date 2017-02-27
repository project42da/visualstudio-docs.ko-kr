---
title: "NotifyDebuggerOfWaitCompletion 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "NotifyDebuggerOfWaitCompletion 메서드를 작업 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# NotifyDebuggerOfWaitCompletion 메서드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거에서 중단점 대상으로 사용 하는 자리 표시자 방법입니다. 이 메서드 인라인 또는 최적화 되지 않아야 합니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
## 구문  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## 설명  
 작업을 작업으로 모든 조인 연산이 해당 디버거 알림 비트가 설정 된 경우이 메서드를 호출 해야 합니다.  
  
## 요구 사항  
  
## 참고 항목  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)
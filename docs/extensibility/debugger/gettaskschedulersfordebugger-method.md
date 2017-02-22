---
title: "GetTaskSchedulersForDebugger 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetTaskSchedulersForDebugger 메서드, TaskScheduler 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# GetTaskSchedulersForDebugger 메서드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

모든 검색 <xref:System.Threading.Tasks.TaskScheduler> 현재 활성화 되어 있는 개체입니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서이 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## 반환 값  
 모든 배열 <xref:System.Threading.Tasks.TaskScheduler> 이 현재 활성화 되어 있는 개체 <xref:System.AppDomain>합니다.  
  
## 설명  
 이 메서드는 스레드로부터 안전 하지 및의 다른 인스턴스에 동시에 사용할 수 없습니다 <xref:System.Threading.Tasks.TaskScheduler>합니다. 디버거는 다른 모든 스레드가 일시 중단 하는 경우에 디버거를 호출 해야 합니다.  
  
## 참고 항목  
 [TaskScheduler 클래스](../../extensibility/debugger/taskscheduler-class-internal-members.md)
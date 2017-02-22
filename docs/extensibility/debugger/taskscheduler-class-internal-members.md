---
title: "TaskScheduler 클래스-내부 멤버 | Microsoft Docs"
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
  - "TaskScheduler 클래스 [.NET Framework 디버그 엔진]"
  - "디버그 엔진, TaskScheduler 클래스 [.NET Framework]"
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# TaskScheduler 클래스-내부 멤버
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 항목의 내부 멤버를 설명 합니다.는 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> 사용자 지정 디버거를 구현 하는 데 도움이 되는 클래스입니다. 이 클래스에 대 한 일반 정보에 대 한 참조는 <xref:System.Threading.Tasks.TaskScheduler> 참조 항목입니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서 이러한 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## 멤버  
  
### 메서드  
  
|이름|설명|  
|--------|--------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|모든 예약 된 작업의 배열을 검색합니다.|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|모든 검색 <xref:System.Threading.Tasks.TaskScheduler> 현재 활성화 되어 있는 개체입니다.|  
  
## 설명  
  
## 참고 항목  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [.NET Framework에 대 한 병렬 확장 기능의 내부](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
---
title: "TASK_STATE_CANCELED 필드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TASK_STATE_CANCELED 필드, 작업 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: f4f5a96a-8230-493d-9696-8d2716bda261
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# TASK_STATE_CANCELED 필드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

작업 실행 상태에 도달 했으므로 하거나 해당 취소를 승인 하 고 예외 없이 완료 전에 취소 되었습니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서이 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.field static assembly literal int32 TASK_STATE_CANCELED = int32(0x00800000)  
```  
  
## 설명  
 하는 경우는 [m\_stateFlags](../../extensibility/debugger/m-stateflags-field.md) 이 값을 포함 하는 필드는 <xref:System.Threading.Tasks.Task.Status%2A> 속성에서 반환 <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>합니다.  
  
## 참고 항목  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)
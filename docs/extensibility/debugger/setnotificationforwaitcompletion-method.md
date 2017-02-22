---
title: "SetNotificationForWaitCompletion 메서드 | Microsoft Docs"
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
  - "SetNotificationForWaitCompletion 메서드를 작업 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# SetNotificationForWaitCompletion 메서드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

설정 하거나 TASK\_STATE\_WAIT\_COMPLETION\_NOTIFICATION 상태 비트를 해제 합니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
## 구문  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### 매개 변수  
 `enabled`  
  
 `true` 비트; 설정 하려면 `false` 에 설정 되지 않은 비트입니다.  
  
## 예외  
  
## 설명  
 디버거는 비동기 메서드 본문에서 단계를 위해이 비트를 설정 합니다. 경우 `enabled` 은 `true`, 아직 완료 되지 않은 작업에 대해서만이 메서드를 호출 해야 합니다. 경우 `enabled` 은 `false`, 완료 된 작업에서이 메서드를 호출할 수 있습니다. 하거나 이벤트에 사용할 promise 스타일 작업에 대 한 합니다.  
  
## 요구 사항  
  
## 참고 항목  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)
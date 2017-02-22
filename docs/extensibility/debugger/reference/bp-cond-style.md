---
title: "BP_COND_STYLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_COND_STYLE"
helpviewer_keywords: 
  - "BP_COND_STYLE 열거형"
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_COND_STYLE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

보류 중단점 조건 스타일을 지정 하 고 중단점을 바인딩할.  
  
## 구문  
  
```cpp#  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```c#  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## Members  
 BP\_COND\_NONE  
 중단점 중단점의 위치에 도달할 때 발생 합니다.  지정 된 중단점 조건 없음입니다.  
  
 BP\_COND\_WHEN\_TRUE  
 평가 때 조건식 중단점에 관련 되는 중단점을 발생 시키는 `true`.  
  
 BP\_COND\_WHEN\_CHANGED  
 중단점은 조건식의 값 중단점에 연관 될 때의 이전 실행에서 변경 된 발생.  
  
## 설명  
 사용 되는 `styleCondition` 의 멤버는 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) 구조.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
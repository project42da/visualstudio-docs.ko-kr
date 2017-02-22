---
title: "BP_PASSCOUNT_STYLE | Microsoft Docs"
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
  - "BP_PASSCOUNT_STYLE"
helpviewer_keywords: 
  - "BP_PASSCOUNT_STYLE 구조"
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_PASSCOUNT_STYLE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

발생 시키는 중단점을 중단 중단점 통과 횟수와 관련 된 조건을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```c#  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## Members  
 BP\_PASSCOUNT\_NONE  
 스타일 없음 중단점 패스 개수를 지정합니다.  
  
 BP\_PASSCOUNT\_EQUAL  
 중단점 패스 개수 스타일 동일 하 게 설정 합니다.  중단점이 적중 될 횟수를 통과 횟수가 되 면 중단점을 발생 시킵니다.  
  
 BP\_PASSCOUNT\_EQUAL\_OR\_GREATER  
 중단점 통과 횟수가 스타일 같거나 큰 수를 설정합니다.  중단점이 적중 될 횟수 패스 개수 크거나 때 중단점을 발생 합니다.  
  
 BP\_PASSCOUNT\_MOD  
 지정 된 나머지 통과 개수.  예를 들어, 통과 횟수입니다 `BP_PASSCOUNT_MOD` 고 통과 수 값 4, 적중된 횟수가 4의 배수가 될 때마다 중단점이 발생 합니다.  
  
## 설명  
 사용 되는 `stylePassCount` 의 멤버는 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) 의 멤버인 구조체는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
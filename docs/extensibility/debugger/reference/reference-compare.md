---
title: "REFERENCE_COMPARE | Microsoft Docs"
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
  - "REFERENCE_COMPARE"
helpviewer_keywords: 
  - "REFERENCE_COMPARE 열거형"
ms.assetid: e31cdc78-f621-498b-9ca4-aefa790b9f6f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# REFERENCE_COMPARE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

비교에 대 한 참조의 형식을 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_REFERENCE_COMPARE {   
   REF_COMPARE_EQUAL        = 0x0001,  
   REF_COMPARE_LESS_THAN    = 0x0002,  
   REF_COMPARE_GREATER_THAN = 0x0003  
};  
typedef DWORD REFERENCE_COMPARE;  
```  
  
```c#  
public enum enum_REFERENCE_COMPARE {   
   REF_COMPARE_EQUAL        = 0x0001,  
   REF_COMPARE_LESS_THAN    = 0x0002,  
   REF_COMPARE_GREATER_THAN = 0x0003  
};  
```  
  
## Members  
 REF\_COMPARE\_EQUAL  
 같지 않음 비교를 지정합니다.  
  
 REF\_COMPARE\_LESS\_THAN  
 작은 지정\-비교 합니다.  
  
 REF\_COMPARE\_GREATER\_THAN  
 보다 큼을 지정\-비교 합니다.  
  
## 설명  
 인수로 전달 되는 [비교](../../../extensibility/debugger/reference/idebugreference2-compare.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [비교](../../../extensibility/debugger/reference/idebugreference2-compare.md)
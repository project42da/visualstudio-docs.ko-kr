---
title: "BP_ERROR_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_ERROR_TYPE"
helpviewer_keywords: 
  - "BP_ERROR_TYPE 열거형"
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_ERROR_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점 오류 유형을 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```c#  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## Members  
 BPET\_NONE  
 중단점 오류를 지정합니다.  
  
 BPET\_TYPE\_WARNING  
 경고 스타일 중단점 오류를 지정합니다.  
  
 BPET\_TYPE\_ERROR  
 오류 스타일 중단점 오류를 지정 합니다.  
  
 BPET\_SEV\_HIGH  
 심각한 중단점 오류를 지정합니다.  
  
 BPET\_SEV\_GENERAL  
 보통 심각도 중단점 오류를 지정합니다.  
  
 BPET\_SEV\_LOW  
 낮은 심각도 중단점 오류를 지정합니다.  
  
 BPET\_TYPE\_MASK  
 마스크 스타일 중단점 오류를 지정합니다.  
  
 BPET\_SEV\_MASK  
 스타일\-마스크 심각도 중단점 오류를 지정합니다.  
  
 BPET\_GENERAL\_WARNING  
 일반 경고 스타일 중단점 오류를 지정합니다.  
  
 BPET\_GENERAL\_ERROR  
 일반 오류 스타일 중단점 오류를 지정합니다.  
  
 BPET\_ALL  
 모든 중단점 오류 형식을 지정합니다.  
  
## 설명  
 이러한 값의 비트와 함께 사용할 수 있습니다 `OR` 사용에 대 한의 `dwType` 의 멤버는 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조.  매개 변수로 전달 되는 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) 메서드.  
  
 중단점 오류 형식 유형 및 심각도의 구성 됩니다.  이 중단점 오류 형식은 일종 되지 않습니다 수 있습니다 \(예를 들어, `BPET_TYPE_ERROR`,\) 또는 심각도 \(예를 들어, `BPET_SEV_GENERAL`\) 단독으로 사용 합니다.  `BPET_GENERAL_WARNING`및 `BPET_GENERAL_ERROR` 일반 오류 및 경고 중단점에 대 한 미리 정의 된 값을 제공 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
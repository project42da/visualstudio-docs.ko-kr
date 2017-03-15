---
title: "GUID_ARRAY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GUID_ARRAY 구조"
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# GUID_ARRAY
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용할 수 있는 디버깅 엔진에 대 한 고유 식별자의 배열에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagGUID_ARRAY  
{  
   DWORD dwCount;  
   GUID *Members;  
} GUID_ARRAY;  
```  
  
```c#  
public struct GUID_ARRAY  
{  
   public uint dwCount;  
   public Guid Members;  
}  
```  
  
## 용어  
 dwCount  
 수의 배열에서 고유한 식별자입니다.  
  
 Members  
 고유 식별자를 포함 하는 배열입니다.  
  
## 설명  
 이 구조에서 반환 되는 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) 메서드.  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)
---
title: "BP_RES_DATA_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_RES_DATA_FLAGS"
helpviewer_keywords: 
  - "BP_RES_DATA_FLAGS 열거형"
ms.assetid: d97611e2-def6-45a9-ad7d-eedf2ad4c82b
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# BP_RES_DATA_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

데이터 중단점을 에뮬레이트한 여부 또는 구현된에 하드웨어를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_RES_DATA_FLAGS {   
   BP_RES_DATA_EMULATED = 0x0001  
};  
typedef DWORD BP_RES_DATA_FLAGS;  
```  
  
```c#  
public enum enum_BP_RES_DATA_FLAGS {   
   BP_RES_DATA_EMULATED = 0x0001  
};  
```  
  
## Members  
 BP\_RES\_DATA\_EMULATED  
 데이터 중단점을 에뮬레이션 되는 지정 합니다.  
  
## 설명  
 사용 되는 `dwFlags` 의 멤버는 [BP\_RESOLUTION\_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) 구조.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_RESOLUTION\_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)
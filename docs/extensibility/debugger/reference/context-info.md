---
title: "CONTEXT_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CONTEXT_INFO"
helpviewer_keywords: 
  - "CONTEXT_INFO 구조"
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# CONTEXT_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조는 메모리 컨텍스트 또는 상황에 맞는 코드를 설명합니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagCONTEXT_INFO {   
   CONTEXT_INFO_FIELDS dwFields;  
   BSTR                bstrModuleUrl;  
   BSTR                bstrFunction;  
   TEXT_POSITION       posFunctionOffset;  
   BSTR                bstrAddress;  
   BSTR                bstrAddressOffset;  
   BSTR                bstrAddressAbsolute;  
} CONTEXT_INFO;  
```  
  
```c#  
public struct CONTEXT_INFO {  
   public uint          dwFields;  
   public string        bstrModuleUrl;  
   public string        bstrFunction;  
   public TEXT_POSITION posFunctionOffset;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrAddressAbsolute;  
};  
```  
  
## Members  
 dwFields  
 그가 플래그의 조합 [CONTEXT\_INFO\_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) 채워진 필드를 지정 하는 열거형**.**  
  
 bstrModuleUrl  
 컨텍스트는 모듈의 이름입니다.  
  
 bstrFunction  
 함수 이름 컨텍스트에 있는 곳입니다.  
  
 posFunctionOffset  
 A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 함수의 코드 컨텍스트와 연결 된 줄 및 열 오프셋을 나타내는 구조입니다.  
  
 bstrAddress  
 주어진된 컨텍스트에 있는 코드 주소입니다.  
  
 bstrAddressOffset  
 주어진된 컨텍스트에 있는 코드 주소 오프셋입니다.  
  
 bstrAddressAbsolute  
 지정 된 컨텍스트의 위치한 메모리에서 절대 주소입니다.  
  
## 설명  
 이 구조에 대 한 호출에서 반환 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) 방법입니다.  
  
 이 구조에 대 한 일반적인 사용을 지원 하 되는  **메모리** 디버그 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT\_INFO\_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)
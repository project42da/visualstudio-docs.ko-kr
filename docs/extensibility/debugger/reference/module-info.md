---
title: "MODULE_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MODULE_INFO"
helpviewer_keywords: 
  - "MODULE_INFO 구조"
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# MODULE_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 모듈 \(DLL, EXE, 또는 어셈블리\)에 대해 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```c#  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## Members  
 dwValidFields  
 플래그의 조합에서 [MODULE\_INFO\_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 m\_bstrName  
 모듈 이름입니다.  
  
 m\_bstrUrl  
 모듈의 URL입니다.  
  
 m\_bstrVersion  
 모듈의 버전입니다.  
  
 m\_bstrDebugMessage  
 이 모듈에 대 한 예를 들어, "기호 로드할 수 없습니다." 메시지를  
  
 m\_addrLoadAddress  
 모듈의 로드 주소입니다.  
  
 m\_addrPreferredLoadAddress  
 모듈이 기본 로드 주소입니다.  
  
 m\_dwSize  
 모듈 크기입니다.  
  
 m\_dwLoadOrder  
 모듈 로드 순서입니다.  
  
 m\_TimeStamp  
 기호 파일을 마지막으로 수정한 시간입니다.  
  
 m\_bstrUrlSymbolLocation  
 기호 파일의 위치 \(예를 들어, "입니다.  \\ "\) 모듈에 지정 합니다.  시작 위치와 모듈에 대 한 기호를 찾으려면 사용 합니다.  
  
 m\_dwModuleFlags  
 플래그의 조합에서 [MODULE\_FLAGS](../../../extensibility/debugger/reference/module-flags.md) 모듈에서 설명 하는 열거형입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) 메서드는 입력 위치에 있습니다.  
  
 이 구조에 나열 된 각 모듈에 해당는  **모듈** 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE\_INFO\_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE\_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
---
title: "FRAMEINFO | Microsoft Docs"
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
  - "FRAMEINFO"
helpviewer_keywords: 
  - "FRAMEINFO 구조"
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# FRAMEINFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스택 프레임에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagFRAMEINFO {   
   FRAMEINFO_FLAGS    m_dwValidFields;  
   BSTR               m_bstrFuncName;  
   BSTR               m_bstrReturnType;  
   BSTR               m_bstrArgs;  
   BSTR               m_bstrLanguage;  
   BSTR               m_bstrModule;  
   UINT64             m_addrMin;  
   UINT64             m_addrMax;  
   IDebugStackFrame2* m_pFrame;  
   IDebugModule2*     m_pModule;  
   BOOL               m_fHasDebugInfo;  
   BOOL               m_fStaleCode;  
   BOOL               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
```c#  
public struct FRAMEINFO {   
   public uint              m_dwValidFields;  
   public string            m_bstrFuncName;  
   public string            m_bstrReturnType;  
   public string            m_bstrArgs;  
   public string            m_bstrLanguage;  
   public string            m_bstrModule;  
   public ulong             m_addrMin;  
   public ulong             m_addrMax;  
   public IDebugStackFrame2 m_pFrame;  
   public IDebugModule2     m_pModule;  
   public int               m_fHasDebugInfo;  
   public int               m_fStaleCode;  
   public int               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
## Members  
 m\_dwValidFields  
 플래그의 조합에서 [FRAMEINFO\_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 필드에 채워져 지정 하는 열거형입니다.  
  
 m\_bstrFuncName  
 스택 프레임과 연결 된 함수의 이름입니다.  
  
 m\_bstrReturnType  
 스택 프레임과 연결 된 반환 형식이 있습니다.  
  
 m\_bstrArgs  
 스택 프레임과 연결 된 함수의 인수입니다.  
  
 m\_bstrLanguage  
 함수가 구현 되는 언어입니다.  
  
 m\_bstrModule  
 스택 프레임과 연결 된 모듈 이름입니다.  
  
 m\_addrMin  
 최소 물리적 스택 주소입니다.  
  
 m\_addrMAX  
 실제 최대 스택 주소입니다.  
  
 m\_pFrame  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 이 스택 프레임을 나타내는 개체입니다.  
  
 m\_pFrame  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 이 스택 프레임을 포함 하는 모듈을 나타내는 개체입니다.  
  
 m\_fHasDebugInfo  
 0이 아닌 \(`TRUE`\) 디버그 정보는 지정 된 프레임에 존재 하는 경우.  
  
 m\_fHasDebugInfo  
 0이 아닌 \(`TRUE`\) 스택 프레임이 더 이상 유효 하지 않은 코드와 관련 된 경우.  
  
 m\_fHasDebugInfo  
 0이 아닌 \(`TRUE`\) 세션 디버그 매니저 \(SDM\) 스택 프레임이 표시 됩니다 경우.  
  
## 설명  
 이 구조체에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) 메서드를 채워야 합니다.  이 구조는 또한 포함 된 목록에 포함 된는 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) ,에 대 한 호출에서 반환 되는 인터페이스는 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO\_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
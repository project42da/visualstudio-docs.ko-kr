---
title: FRAMEINFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5b3fd52fb80cd2bd588951b6a921ca157935a3a2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="frameinfo"></a>FRAMEINFO
스택 프레임에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
## <a name="members"></a>멤버  
 m_dwValidFields  
 플래그의 조합 된 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 어떤 필드 입력을 지정 하는 열거형입니다.  
  
 m_bstrFuncName  
 스택 프레임와 관련 된 함수 이름입니다.  
  
 m_bstrReturnType  
 스택 프레임와 관련 된 반환 형식입니다.  
  
 m_bstrArgs  
 인수는 스택 프레임을 연관 된 함수입니다.  
  
 m_bstrLanguage  
 함수를 구현 하는 언어입니다.  
  
 m_bstrModule  
 스택 프레임과 연결 된 모듈 이름입니다.  
  
 m_addrMin  
 최소 실제 스택 주소입니다.  
  
 m_addrMAX  
 최대 물리적 스택 주소입니다.  
  
 m_pFrame  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 이 스택 프레임을 나타내는 개체입니다.  
  
 m_pFrame  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 이 스택 프레임을 포함 하는 모듈을 나타내는 개체입니다.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 특정된 프레임에 디버그 정보가 있는 경우.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 스택 프레임은 더 이상 코드와 연결 하는 경우.  
  
 m_fHasDebugInfo  
 0이 아닌 (`TRUE`) 스택 프레임 세션 디버그 관리자 (SDM) 주석을 처리 하는 경우.  
  
## <a name="remarks"></a>설명  
 이 구조에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) 메서드를 입력 합니다. 이 구조에 포함 된 목록에도 포함 됩니다는 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 차례로 호출에서 반환 되는 인터페이스는 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
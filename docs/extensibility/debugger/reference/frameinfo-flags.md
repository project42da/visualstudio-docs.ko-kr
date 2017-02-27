---
title: "FRAMEINFO_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FRAMEINFO_FLAGS"
helpviewer_keywords: 
  - "FRAMEINFO_FLAGS 열거형"
ms.assetid: 41578062-8455-412a-9d8b-1e1e9dc8d52e
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# FRAMEINFO_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스택 프레임 개체에 대 한 검색 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_FRAMEINFO_FLAGS {  
   FIF_FUNCNAME              = 0x00000001,  
   FIF_RETURNTYPE            = 0x00000002,  
   FIF_ARGS                  = 0x00000004,  
   FIF_LANGUAGE              = 0x00000008,  
   FIF_MODULE                = 0x00000010,  
   FIF_STACKRANGE            = 0x00000020,  
   FIF_FRAME                 = 0x00000040,  
   FIF_DEBUGINFO             = 0x00000080,  
   FIF_STALECODE             = 0x00000100,  
   FIF_ANNOTATEDFRAME        = 0x00000200,  
   FIF_DEBUG_MODULEP         = 0x00000400,  
   FIF_FUNCNAME_FORMAT       = 0x00001000,  
   FIF_FUNCNAME_RETURNTYPE   = 0x00002000,  
   FIF_FUNCNAME_ARGS         = 0x00004000,  
   FIF_FUNCNAME_LANGUAGE     = 0x00008000,  
   FIF_FUNCNAME_MODULE       = 0x00010000,  
   FIF_FUNCNAME_LINES        = 0x00020000,  
   FIF_FUNCNAME_OFFSET       = 0x00040000,  
   FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,  
   FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,  
   FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,  
   FIF_FUNCNAME_ARGS_ALL     = 0x00700000,  
   FIF_ARGS_TYPES            = 0x01000000,  
   FIF_ARGS_NAMES            = 0x02000000,  
   FIF_ARGS_VALUES           = 0x04000000,  
   FIF_ARGS_ALL              = 0x07000000,  
   FIF_ARGS_NOFORMAT         = 0x08000000,  
   FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,  
   FIF_FILTER_NON_USER_CODE  = 0x20000000,  
   FIF_ARGS_NO_TOSTRING      = 0x40000000,  
   FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000  
};  
typedef DWORD FRAMEINFO_FLAGS;  
```  
  
```c#  
public enum enum_FRAMEINFO_FLAGS {  
   FIF_FUNCNAME              = 0x00000001,  
   FIF_RETURNTYPE            = 0x00000002,  
   FIF_ARGS                  = 0x00000004,  
   FIF_LANGUAGE              = 0x00000008,  
   FIF_MODULE                = 0x00000010,  
   FIF_STACKRANGE            = 0x00000020,  
   FIF_FRAME                 = 0x00000040,  
   FIF_DEBUGINFO             = 0x00000080,  
   FIF_STALECODE             = 0x00000100,  
   FIF_ANNOTATEDFRAME        = 0x00000200,  
   FIF_DEBUG_MODULEP         = 0x00000400,  
   FIF_FUNCNAME_FORMAT       = 0x00001000,  
   FIF_FUNCNAME_RETURNTYPE   = 0x00002000,  
   FIF_FUNCNAME_ARGS         = 0x00004000,  
   FIF_FUNCNAME_LANGUAGE     = 0x00008000,  
   FIF_FUNCNAME_MODULE       = 0x00010000,  
   FIF_FUNCNAME_LINES        = 0x00020000,  
   FIF_FUNCNAME_OFFSET       = 0x00040000,  
   FIF_FUNCNAME_ARGS_TYPES   = 0x00100000,  
   FIF_FUNCNAME_ARGS_NAMES   = 0x00200000,  
   FIF_FUNCNAME_ARGS_VALUES  = 0x00400000,  
   FIF_FUNCNAME_ARGS_ALL     = 0x00700000,  
   FIF_ARGS_TYPES            = 0x01000000,  
   FIF_ARGS_NAMES            = 0x02000000,  
   FIF_ARGS_VALUES           = 0x04000000,  
   FIF_ARGS_ALL              = 0x07000000,  
   FIF_ARGS_NOFORMAT         = 0x08000000,  
   FIF_ARGS_NO_FUNC_EVAL     = 0x10000000,  
   FIF_FILTER_NON_USER_CODE  = 0x20000000,  
   FIF_ARGS_NO_TOSTRING      = 0x40000000,  
   FIF_DESIGN_TIME_EXPR_EVAL = 0x80000000  
};  
```  
  
## Members  
 FIF\_FUNCNAME  
 초기화\/사용의 `m_bstrFuncName` 필드입니다.  
  
 FIF\_RETURNTYPE  
 초기화\/사용의 `m_bstrReturnType` 필드입니다.  
  
 FIF\_ARGS  
 초기화\/사용의 `m_bstrArgs` 필드입니다.  
  
 FIF\_LANGUAGE  
 초기화\/사용의 `m_bstrLanguage` 필드입니다.  
  
 FIF\_MODULE  
 초기화\/사용의 `m_bstrModule` 필드입니다.  
  
 FIF\_STACKRANGE  
 초기화\/사용의 `m_addrMin` 및 `m_addrMax` \(스택 범위\) 필드입니다.  
  
 FIF\_FRAME  
 초기화\/사용의 `m_pFrame` 필드입니다.  
  
 FIF\_DEBUGINFO  
 초기화\/사용의 `m_fHasDebugInfo` 필드입니다.  
  
 FIF\_STALECODE  
 초기화\/사용의 `m_fStaleCode` 필드입니다.  
  
 FIF\_ANNOTATEDFRAME  
 초기화\/사용의 `m_fAnnotatedFrame` 필드입니다.  
  
 FIF\_DEBUG\_MODULEP  
 초기화\/사용의 `m_pModule` 필드입니다.  
  
 FIF\_FUNCNAME\_FORMAT  
 함수 이름 형식을 지정합니다.  결과에 반환 되는 `m_bstrFunName` 필드 및 필드가 없습니다 채워진.  
  
 FIF\_FUNCNAME\_RETURNTYPE  
 반환 형식에 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_ARGS  
 인수를 더는 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_LANGUAGE  
 추가 언어에 있는 `m_bstrFuncName` 필드.  
  
 FIF\_FUNCNAME\_MODULE  
 모듈 이름에 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_LINES  
 에 줄 수 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_OFFSET  
 추가 `m_bstrFuncName` 경우에 줄의 시작 부분에서 바이트 오프셋 필드 `FIF_FUNCNAME_LINES` 지정 됩니다.  경우 `FIF_FUNCNAME_LINES` 지정 되지 않은 경우 또는 줄 번호를 사용할 수 없는 경우 함수의 시작부터 바이트 오프셋을 추가 합니다.  
  
 FIF\_FUNCNAME\_ARGS\_TYPES  
 각 함수 인수에 유형을 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_ARGS\_NAMES  
 각 함수 인수에 이름 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_ARGS\_VALUES  
 각 함수 인수에 값을 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF\_FUNCNAME\_ARGS\_ALL  
 추가 형식, 이름 및 값에 대 한 모든 인수는 `m_bstrFuncName` 필드.  
  
 FIF\_ARGS\_TYPES  
 인수 형식 가져와 서식이 지정 됩니다.  
  
 FIF\_ARGS\_NAMES  
 인수 이름은 검색 하며 포맷 합니다.  
  
 FIF\_ARGS\_VALUES  
 인수 값 검색 포맷 하 고 있습니다.  
  
 FIF\_ARGS\_ALL  
 검색 하 고 형식, 이름 및 값의 모든 인수 형식을 지정 합니다.  
  
 FIF\_ARGS\_NOFORMAT  
 인수는 않습니다 포맷 된 지정 \(예를 들어 하지 않는 인수 목록 주위에 괄호를 추가 나 인수 사이의 구분 기호를 추가\).  
  
 FIF\_ARGS\_NO\_FUNC\_EVAL  
 \(속성\) 함수 인수의 값을 검색할 때 사용할 수 없습니다 것을 지정 합니다.  
  
 FIF\_FILTER\_NON\_USER\_CODE  
 디버그 엔진 필터링 디버거용 코드 프레임 포함 되지 않은 것입니다.  
  
 FIF\_ARGS\_NO\_TOSTRING  
 허용 하지 않는 작업 `ToString()` 평가 또는 서식 함수 인수를 반환 하는 경우 작동 합니다.  
  
 FIF\_DESIGN\_TIME\_EXPR\_EVAL  
 호스팅 프로세스 대신 호스트 응용 프로그램 도메인에서 프레임 정보를 얻을 수 있어야 합니다.  
  
## 설명  
 이러한 플래그를 전달의 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 및 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) 필드를 초기화 하는 나타내기 위해 메서드는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조 또는 구조.  
  
 이러한 플래그 필드를 나타내는 데도 사용 됩니다 있는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조는 유효 하 고 사용 하는 구조를 반환 하는 경우.  이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)
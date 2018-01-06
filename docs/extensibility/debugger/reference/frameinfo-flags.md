---
title: FRAMEINFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FRAMEINFO_FLAGS
helpviewer_keywords: FRAMEINFO_FLAGS enumeration
ms.assetid: 41578062-8455-412a-9d8b-1e1e9dc8d52e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9efeaee3ab2a2f7762c1ae3b95ae7548091dfe0b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="frameinfoflags"></a>FRAMEINFO_FLAGS
검색할 스택 프레임 개체에 대 한 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_FRAMEINFO_FLAGS {  
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
  
```csharp  
public enum enum_FRAMEINFO_FLAGS {  
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
  
## <a name="members"></a>멤버  
 FIF_FUNCNAME  
 초기화/사용 된 `m_bstrFuncName` 필드입니다.  
  
 FIF_RETURNTYPE  
 초기화/사용 된 `m_bstrReturnType` 필드입니다.  
  
 FIF_ARGS  
 초기화/사용 된 `m_bstrArgs` 필드입니다.  
  
 FIF_LANGUAGE  
 초기화/사용 된 `m_bstrLanguage` 필드입니다.  
  
 FIF_MODULE  
 초기화/사용 된 `m_bstrModule` 필드입니다.  
  
 FIF_STACKRANGE  
 초기화/사용 된 `m_addrMin` 및 `m_addrMax` (스택 범위) 필드입니다.  
  
 FIF_FRAME  
 초기화/사용 된 `m_pFrame` 필드입니다.  
  
 FIF_DEBUGINFO  
 초기화/사용 된 `m_fHasDebugInfo` 필드입니다.  
  
 FIF_STALECODE  
 초기화/사용 된 `m_fStaleCode` 필드입니다.  
  
 FIF_ANNOTATEDFRAME  
 초기화/사용 된 `m_fAnnotatedFrame` 필드입니다.  
  
 FIF_DEBUG_MODULEP  
 초기화/사용 된 `m_pModule` 필드입니다.  
  
 FIF_FUNCNAME_FORMAT  
 함수 이름 형식을 지정합니다. 결과에 반환 됩니다는 `m_bstrFunName` 필드와 다른 필드가 작성 됩니다.  
  
 FIF_FUNCNAME_RETURNTYPE  
 반환 형식이 추가 된 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_ARGS  
 추가 대 한 인수는 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_LANGUAGE  
 언어를 추가 하는 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_MODULE  
 모듈 이름에 추가 하는 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_LINES  
 추가 하는 줄 수는 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_OFFSET  
 에 추가 `m_bstrFuncName` 경우 줄의 시작 부분부터 바이트 오프셋 필드 `FIF_FUNCNAME_LINES` 지정 됩니다. 경우 `FIF_FUNCNAME_LINES` 를 지정 하지 않으면 줄 번호를 사용할 수 없는 경우 추가 하는 오프셋 (바이트)는 함수 시작 부분에서 또는 합니다.  
  
 FIF_FUNCNAME_ARGS_TYPES  
 각 함수 인수를 형식에 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_ARGS_NAMES  
 각 함수 인수 이름을 추가 하는 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_ARGS_VALUES  
 각 함수 인수에 값 추가 `m_bstrFuncName` 필드입니다.  
  
 FIF_FUNCNAME_ARGS_ALL  
 추가 유형, 이름 및 값에 대 한 모든 인수는 `m_bstrFuncName` 필드입니다.  
  
 FIF_ARGS_TYPES  
 인수 형식이 검색 되 고 형식이 지정 됩니다.  
  
 FIF_ARGS_NAMES  
 인수 이름 검색 및 서식이 지정 됩니다.  
  
 FIF_ARGS_VALUES  
 인수 값 검색 및 서식이 지정 됩니다.  
  
 FIF_ARGS_ALL  
 검색 및 유형, 이름 및 값의 모든 인수 형식을 지정 합니다.  
  
 FIF_ARGS_NOFORMAT  
 인수 형식이 수지 않습니다 지정 (예를 들어 수행 하지 열기와 닫기 괄호는 인수 목록을 추가 하거나 수 없는 인수 사이의 구분 기호를 추가).  
  
 FIF_ARGS_NO_FUNC_EVAL  
 함수 (속성) 평가 사용 하지 않도록 인수 값을 검색할 때 지정 합니다.  
  
 FIF_FILTER_NON_USER_CODE  
 디버그 엔진 포함 되기 때문에 사용자 코드가 아닌 프레임을 필터링 하는 것입니다.  
  
 FIF_ARGS_NO_TOSTRING  
 허용 안 함 `ToString()` 함수 평가 또는 함수 인수를 반환 하는 경우의 형식을 지정 합니다.  
  
 FIF_DESIGN_TIME_EXPR_EVAL  
 호스팅 프로세스를 사용 하지 않고 호스팅된 응용 프로그램 도메인에서 프레임 정보를 참조 해야 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 플래그에 전달 되는 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 및 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) 를 초기화할 수 있는 필드를 나타내는 방법은 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조 또는 구조입니다.  
  
 이러한 플래그의 필드를 나타내기 위해 사용도 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조는 사용 되지 않으며 유효한 구조를 반환 하는 경우. 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)
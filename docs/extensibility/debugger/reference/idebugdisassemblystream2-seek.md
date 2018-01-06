---
title: IDebugDisassemblyStream2::Seek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDisassemblyStream2::Seek
helpviewer_keywords: IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2725eb876cf66665c27027dd4d9b250ed7e866e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
디스어셈블리 스트림에서 지정된 된 수의 지정된 된 위치에 상대적인 지침 읽기 포인터를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSeekStart`  
 [in] 값은 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) seek 프로세스를 시작 하려면 상대 위치를 지정 하는 열거형입니다.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 기준으로 seek 연산을 코드 컨텍스트를 나타내는 개체입니다. 경우에이 매개 변수는 `dwSeekStart`  =  `SEEK_START_CODECONTEXT`, 그렇지 않으면이 매개 변수는 무시 되 고 null 값이 될 수 있습니다.  
  
 `uCodeLocationId`  
 [in] 기준으로 seek 연산을 코드 위치 식별자입니다. 경우이 매개 변수는 `dwSeekStart`  =  `SEEK_START_CODELOCID`, 그렇지 않으면이 매개 변수는 무시 되 고 0으로 설정할 수 있습니다. 에 대 한 설명 섹션을 참조는 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) 방법에 대 한 설명은 코드 위치 식별자입니다.  
  
 `iInstructions`  
 [in] 에 지정 된 위치를 기준으로 이동 하는 명령 수가 `dwSeekStart`합니다. 이 값 뒤로 이동 음수일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` seek 위치 되었으면는 목록에 나오지 지점에서 사용 가능한 지침입니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 목록의 시작 부분 앞 위치로 seek 되었으면 읽기 위치 목록에서 첫 번째 명령으로 설정 됩니다. 목록의 끝 후 위치로 했습니다. 참조, 읽기 위치 설정 됩니다 마지막 명령 목록.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)
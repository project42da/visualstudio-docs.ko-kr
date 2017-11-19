---
title: "Ijsdebugprocess:: Createbreakpoint 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugProcess.CreateBreakPoint
apilocation: jscript9diag.dll
ms.assetid: a2cb4233-2846-4d11-aa13-21de43abda9f
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10d734f32d092d341dbb1b02a5cc7a0c127223a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugprocesscreatebreakpoint-method"></a>IJsDebugProcess::CreateBreakPoint 메서드
지정한 문서 위치에서 중단점을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateBreakPoint(  
   UINT64 documentId,  
   DWORD characterOffset,  
   DWORD characterCount,  
   BOOL isEnabled,  
   IJsDebugBreakPoint **ppDebugBreakPoint  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `documentId`  
 [in] IDebugDocumentText에 대 한 포인터입니다.  
  
 `characterOffset`  
 [in] 파일의 시작 부분에서 문자 오프셋입니다.  
  
 `characterCount`  
 [in] 중단점을 삽입 해야 하는 문서 텍스트의 길이입니다.  
  
 `isEnabled`  
 [in] 중단점이 활성화 되어 있는지 여부를 지정 합니다.  
  
 `ppDebugBreakPoint`  
 [out] 생성 된 중단점을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugProcess 인터페이스](../../winscript/reference/ijsdebugprocess-interface.md)
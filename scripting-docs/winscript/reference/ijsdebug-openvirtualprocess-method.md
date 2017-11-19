---
title: "Ijsdebug:: Openvirtualprocess 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJSDebug.OpenVirtualProcess
apilocation: jscript9diag.dll
ms.assetid: 5612bf1b-a4e3-4eaf-ac5e-c2e1f147c395
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f5acb137337e46a6e84f7d68c9330a3ca847f2e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugopenvirtualprocess-method"></a>IJsDebug::OpenVirtualProcess 메서드
팩터리 메서드를 새 가상 프로세스 개체를 만드는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
 HRESULT OpenVirtualProcess(  
   DWORD processId,  
   UINT64 runtimeJsBaseAddress,  
   IJsDebugDataTarget *pDataTarget,  
   IJsDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `processId`  
 [in] 디버거를 연결 하는 프로세스 Id입니다.  
  
 `runtimeJsBaseAddress`  
 [in] JavaScript 런타임이 대상 프로세스에 로드 하는 기본 주소입니다.  
  
 `pDataTarget`  
 [in] 디버거 프로세스의 상태에 대 한 쿼리를 제공 된 인터페이스입니다.  
  
 `ppProcess`  
 [out] 새 디버그 프로세스 개체  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 Jscript9diag 및 Jscript9 일치 하지 않는 경우 E_JsDEBUG_MISMATCHED_RUNTIME를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebug 인터페이스](../../winscript/reference/ijsdebug-interface.md)
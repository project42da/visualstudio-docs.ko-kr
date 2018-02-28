---
title: IActiveScript::AddTypeLib | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScript.AddTypeLib
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_AddTypeLib
ms.assetid: 8e507ea8-c80a-471c-b482-ae753c6e8595
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2be7cf033b4b5dd4d99b19a3b71ed53e32af855
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptaddtypelib"></a>IActiveScript::AddTypeLib
스크립트에 대 한 네임 스페이스에 형식 라이브러리를 추가합니다. 이 비슷합니다는 `#include` C/c + +에서 지시문입니다. 클래스 정의 같은 미리 정의 된 항목의 집합을 통해 `typedefs`, 명명 된 스크립트에 사용할 수 있는 런타임 환경에 추가할 상수 및 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddTypeLib(  
    REFGUID guidTypeLib,  // CLSID of type library  
    DWORD dwMaj,          // major version number  
    DWORD dwMin,          // minor version number  
    DWORD dwFlags         // option flags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidTypeLib`  
 [in] 추가 된 형식 라이브러리의 CLSID입니다.  
  
 `dwMaj`  
 [in] 주 버전 번호입니다.  
  
 `dwMin`  
 [in] 부 버전 번호입니다.  
  
 `dwFlags`  
 [in] 옵션 플래그입니다. 다음과 같을 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTTYPELIB_ISCONTROL|형식 라이브러리에 호스트에서 사용 하는 ActiveX 컨트롤에 설명 합니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
|`TYPE_E_CANTLOADLIBRARY`|지정된 된 형식 라이브러리를 로드할 수 없습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
---
title: IActiveScriptAuthor::GetInfoFromContext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetInfoFromContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetInfoFromContext
ms.assetid: 9891b095-6eb5-4473-87c0-c2e5cd2afc1a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 27c13dbe51bb1150554275b5fbeacd00be2e445f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetinfofromcontext"></a>IActiveScriptAuthor::GetInfoFromContext
반환 코드 블록에 지정 된 문자에 대 한 앵커 위치 및 정보를 입력합니다. IntelliSense, 전역 목록, 및 매개 변수 팁 멤버에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetInfoFromContext(  
   LPCOLESTR  pszCode,  
   ULONG      cchCode,  
   ULONG      ichCurrentPosition,  
   DWORD      dwListTypesRequested,  
   DWORD      *pdwListTypesProvided,  
   ULONG      *pichListAnchorPosition,  
   ULONG      *pichFuncAnchorPosition,  
   MEMBERID   *pmemid,  
   LONG       *piCurrentParameter,  
   IUnknown   **ppunk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszCode`  
 [in] 정보 결과 생성 하는 데 사용 하는 코드 블록 문자열의 주소입니다.  
  
 `cchCode`  
 [in] 코드 블록의 길이입니다.  
  
 `ichCurrentPosition`  
 [in] 블록의 시작을 기준으로 문자의 위치입니다.  
  
 `dwListTypesRequested`  
 [in] 요청 된 목록 형식입니다. 다음 값의 조합 될 수 있습니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_NOLIST|0x0000|목록이 없습니다.|  
|SCRIPT_CMPL_MEMBERLIST|0x0001|멤버 목록입니다.|  
|SCRIPT_CMPL_ENUMLIST|0x0002|Enum 목록입니다.|  
|SCRIPT_CMPL_PARAMLIST|0x0004|메서드 매개 변수 목록을 호출 합니다.|  
|SCRIPT_CMPL_GLOBALLIST|0x0008|전역 목록입니다.|  
  
 SCRIPT_CMPL_GLOBALLIST 형식은 다른 완료 항목 OR 연산자를 사용 하 여 결합 될 수 있는 기본 완성 항목으로 처리 됩니다. 먼저 엔진을 제작 하는 스크립트는 다른 완성 목록 항목에 대 한 형식 정보를 입력 하려고 합니다. 실패할 경우 엔진은 SCRIPT_CMPL_GLOBALLIST를 채웁니다.  
  
 `pdwListTypesProvided`  
 [out] 제공 된 목록 형식입니다.  
  
 `pichListAnchorPosition`  
 [out] 시작 인덱스의 현재 위치를 포함 하는 컨텍스트입니다. 인덱스는 시작 블록의 시작을 기준으로 합니다.  
  
 이 채워지는 경우에만 `dwListTypesRequested` SCRIPT_CMPL_MEMBERLIST, SCRIPT_CMPL_ENUMLIST, 또는 SCRIPT_CMPL_GLOBALLIST 포함 됩니다. 다른 요청 된 목록의 형식에 대 한 결과 정의 되지 않습니다.  
  
 `pichFuncAnchorPosition`  
 [out] 현재 위치를 포함 하는 함수 호출의 시작 인덱스입니다. 인덱스는 시작 블록의 시작을 기준으로 합니다.  
  
 현재 위치를 포함 하는 컨텍스트는 함수 호출 일 경우에이 채워집니다 `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST 포함 됩니다. 그렇지 않으면 결과가 정의 되지 않습니다.  
  
 `pmemid`  
 [out] 형식에 의해 정의 된 대로 함수의 MEMBERID는 `IProvideMultipleClassInfo``ppunk` out 매개 변수입니다.  
  
 이 채워지는 경우에만 `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST 포함 됩니다.  
  
 `piCurrentParameter`  
 [out] 인덱스의 현재 위치를 포함 하는 매개 변수입니다. 현재 위치 함수 이름에 포함 된 경우-1이 반환 됩니다.  
  
 `piCurrentParameter` 값이 채워지면 경우에만 `dwListTypesRequested` SCRIPT_CMPL_PARAMLIST 포함 됩니다.  
  
 `ppunk`  
 형식으로 제공 되는 형식 정보는 `IProvideMultipleClassInfo` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IProvideMultipleClassInfo 인터페이스](https://msdn.microsoft.com/library/microsoft.visualstudio.ole.interop.iprovidemultipleclassinfo.aspx)   
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
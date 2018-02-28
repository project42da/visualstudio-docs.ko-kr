---
title: IActiveScriptAuthor::AddScriptlet | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddScriptlet
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddScriptlet
ms.assetid: 879a6651-f187-4934-b130-c1247549900b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b21f906a73a313bf775683ba63738adb25af0007
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthoraddscriptlet"></a>IActiveScriptAuthor::AddScriptlet
루트 수준의 자식으로 추가 하는 코드 스크립틀릿 `IScriptNode` 개체입니다. 호스트는 스크립틀릿의 정규화 된 이름은 수준은 수는 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddScriptlet(  
   LPCOLESTR pszDefaultName,  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszSubItemName,  
   LPCOLESTR pszEventName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszDefaultName`  
 [in] 주소는 스크립틀릿와 연결할 기본 이름입니다.  
  
 `pszCode`  
 [in] 스크립틀릿 텍스트의 주소입니다.  
  
 `pszItemName`  
 [in] 최상위 호스트에서 스크립틀릿 정규화 된 이름 식별자의 버퍼 주소입니다.  
  
 `pszSubItemName`  
 [in] 호스트에서 정규화 된 스크립틀릿 이름의 2-수준 식별자의 버퍼 주소입니다. 이름에는 하나의 수준만 경우 NULL로 설정 합니다.  
  
 `pszEventName`  
 [in] 스크립틀릿은 이벤트 처리기는 이벤트 이름을 포함 하는 버퍼의 주소입니다.  
  
 `pszDelimiter`  
 [in] 주소는 끝의 스크립트 블록 구분 기호입니다. 때 `pszCode` 구문 분석할 텍스트의 스트림에서 호스트가 일반적으로 사용 하는 구분 기호 (예: 두 개의 작은따옴표), 스크립트 블록의 끝을 검색 합니다. 구분 기호는 스크립트 블록의 끝을 표시 하지 않는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `dwCookie`  
 [in] 스크립틀릿 호스트 개체와 연결 하는 데 사용 되는 응용 프로그램 정의 값입니다.  
  
 `dwFlags`  
 [in] 사용 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
---
title: IActiveScriptAuthor::GetScriptletTextAttributes | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetScriptletTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetScriptletTextAttributes
ms.assetid: 082edfce-6c5b-4e5e-b942-31b423a4fa1d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b01fba7d0e8eb80fed51b1ff0ebd3a8816bacb01
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetscriptlettextattributes"></a>IActiveScriptAuthor::GetScriptletTextAttributes
스크립틀릿의 텍스트 특성을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScriptletTextAttributes(  
   LPCOLESTR pszCode,  
   ULONG cch,  
   LPCOLESTR pszDelimiter,  
   DWORD dwFlags,  
   SOURCE_TEXT_ATTR *pattr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszCode`  
 [에 size_is (`cch`)] 스크립틀릿 텍스트입니다. 이 문자열은 종료 null이 될 필요가 없습니다.  
  
 `cch`  
 [in] 에 사용 되는 크기는 `pszCode` 및 `pattr` 매개 변수입니다.  
  
 `pszDelimiter`  
 [in] 주소는 스크립틀릿 끝 구분 기호입니다. 때 `pszCode` 구문 분석할 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 (예: 두 개의 작은따옴표), 구분 기호는 스크립틀릿의 끝을 검색 합니다. 구분 기호는 스크립틀릿의 끝을 식별 하는 데 사용 되는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `dwFlags`  
 [in] 텍스트 특성은 스크립틀릿을 연관 된 플래그입니다. 다음 값의 조합 수 있습니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|SOURCETEXT_ATTR_IDENTIFIER 특성이 있는 식별자를 식별 하 고 SOURCETEXT_ATTR_MEMBERLOOKUP 특성이 있는 점 연산자를 식별 합니다.|  
|GETATTRFLAG_THIS|0x0100|SOURCETEXT_ATTR_THIS 특성이 있는 현재 개체를 식별 합니다.|  
|GETATTRFLAG_HUMANTEXT|0x8000|SOURCETEXT_ATTR_HUMANTEXT 특성을 가진 문자열 콘텐츠 및 메모 텍스트를 식별 합니다.|  
  
 `pattr`  
 [out에 size_is (`cch`)] 스크립틀릿 코드에 대 한 색상 정보입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::GetScriptTextAttributes](../../winscript/reference/iactivescriptauthor-getscripttextattributes.md)   
 [SOURCE_TEXT_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)
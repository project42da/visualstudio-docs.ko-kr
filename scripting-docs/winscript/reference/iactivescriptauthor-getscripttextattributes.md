---
title: IActiveScriptAuthor::GetScriptTextAttributes | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetScriptTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetScriptTextAttributes
ms.assetid: a53451de-cc5c-4b53-8e5f-81e196364caf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aa96623b4356f0a3d17c8b2631840953dac2d51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetscripttextattributes"></a>IActiveScriptAuthor::GetScriptTextAttributes
스크립트 블록에 대 한 텍스트 특성을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScriptTextAttributes(  
    LPCOLESTR        pszCode,  
    ULONG            cch,  
    LPCOLESTR        pszDelimiter,  
    DWORD            dwFlags,  
    SOURCE_TEXT_ATTR *pattr);  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszCode`  
 [에 size_is (`cch`)] 스크립트 블록의 텍스트입니다. 이 문자열은 종료 null이 될 필요가 없습니다.  
  
 `cch`  
 [in] 에 사용 되는 크기는 `pszCode` 및 `pattr` 매개 변수입니다.  
  
 `pszDelimiter`  
 [in] 주소는 끝의 스크립트 구분 기호입니다. 때 `pszCode` 구문 분석할 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 (예: 두 개의 작은따옴표), 구분 기호는 스크립틀릿의 끝을 검색 합니다. 구분 기호가 없음을 스크립트 블록의 끝을 식별 하는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `dwFlags`  
 [in] 스크립트 블록의 텍스트 특성와 관련 된 플래그입니다. 다음 값의 조합 될 수 있습니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|SOURCETEXT_ATTR_IDENTIFIER 특성이 있는 식별자를 식별 하 고 SOURCETEXT_ATTR_MEMBERLOOKUP 특성이 있는 점 연산자를 식별 합니다.|  
|GETATTRFLAG_THIS|0x0100|SOURCETEXT_ATTR_THIS 특성이 있는 현재 개체를 식별 합니다.|  
|GETATTRFLAG_HUMANTEXT|0x8000|SOURCETEXT_ATTR_HUMANTEXT 특성을 가진 문자열 콘텐츠 및 메모 텍스트를 식별 합니다.|  
  
 `pattr`  
 [out에 size_is (`cch`)] 스크립트 블록 코드에 대 한 색 정보입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [SOURCE_TEXT_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)
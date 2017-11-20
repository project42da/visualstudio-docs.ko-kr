---
title: IActiveScriptAuthor::ParseScriptText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.ParseScriptText
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::ParseScriptText
ms.assetid: ebe212e8-6789-423d-ad22-92be984dc7ad
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 13e81d96ae817b2117f12cb56fd59759f4c2b849
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorparsescripttext"></a>IActiveScriptAuthor::ParseScriptText
스크립트 텍스트를 구문 분석 엔진을 제작 하는 스크립트에 텍스트를 추가 하 고 만듭니다는 `IScriptEntry` 스크립트 블록에 해당 하는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ParseScriptText(  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszCode`  
 [in] 스크립트 텍스트를 구문 분석 합니다.  
  
 `pszItemName`  
 [in] 스크립트 블록에 연결 된 항목 이름을 포함 하는 버퍼 주소입니다.  
  
 `pszDelimiter`  
 [in] 주소는 끝의 스크립트 블록 구분 기호입니다. 때 `pszCode` 구문 분석할 텍스트의 스트림에서 호스트가 일반적으로 사용 하는 구분 기호 (예: 두 개의 작은따옴표), 스크립트 블록의 끝을 검색 합니다. 구분 기호가 없음을 스크립트 블록의 끝을 식별 하는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `dwCookie`  
 [in] 새 연결 되는 응용 프로그램 정의 값 `IScriptEntry` 개체입니다.  
  
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
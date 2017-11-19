---
title: IActiveScriptAuthor::GetLanguageFlags | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.GetLanguageFlags
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::GetLanguageFlags
ms.assetid: eb244452-62f7-4a73-b48f-1aa05cbcc32d
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6137f1cd77d2f305a9ff9d51ac49c214e4c4237b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetlanguageflags"></a>IActiveScriptAuthor::GetLanguageFlags
언어 정보를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLanguageFlags(  
   DWORD              *pgrfasa  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pgrfasa`  
 [out] 언어 정보를 포함 하는 플래그입니다. 다음 값의 조합 될 수 있습니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|fasaPreferInternalHandler|0x0001|언어 응용 프로그램 대신 엔진을 제작 하는 스크립트에 스크립트 이벤트 처리기 만들기를 선호 합니다.|  
|fasaSupportInternalHandler|0x0002|언어 엔진을 제작 하는 스크립트로 만든 스크립트 이벤트 처리기를 지원 합니다.|  
|fasaCaseSensitive|0x0004|스크립트 언어는 대/소문자 구분입니다.|  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 스크립트 엔진 제작 이벤트 처리기를 관리 하는 경우에 응용 프로그램 호출 해야 `CreateChildHandler` 에서 `IScriptEntry` 개체입니다. 그렇기 때문에 프로그램 `IScriptScriptlet` 이벤트 처리기에 해당 하는 개체입니다. 또한 엔진 스크립트 항목에 이벤트 처리기를 추가합니다. 이벤트 처리기는 지정 된 서명 정보를 포함 하는 빈 함수입니다.  
  
 이벤트 처리기를 응용 프로그램을 관리 하는 경우 호출 해야 `CreateChildHandler` 에서 `IScriptNode` 이벤트 처리기 스크립틀릿을 나타내는 개체입니다. 그렇기 때문에 프로그램 `IScriptScriptlet` 이벤트 처리기 스크립틀릿와 연결 된 개체입니다. 응용 프로그램도 이벤트로 빈 함수를 추가 하는 경우 새 처리기 또는 기존 `IScriptEntry` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
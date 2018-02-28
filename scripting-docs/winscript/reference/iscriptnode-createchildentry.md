---
title: 'IScriptNode:: CreateChildEntry | Microsoft Docs'
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptNode. CreateChildEntry
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::CreateChildEntry
ms.assetid: b9682505-4457-40e9-8691-235843637506
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8fcc010efe8fcf30a8f467dd94befff54bc5fac5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnode-createchildentry"></a>IScriptNode:: CreateChildEntry
자식 인스턴스 추가 `IScriptEntry`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateChildEntry(  
   ULONG              isn,  
   DWORD              dwCookie,  
   LPCOLESTR          pszDelimiter,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `isn`  
 [in] 부모에서 자식 요소의 인덱스입니다.  
  
 `dwCookie`  
 [in] 호스트 개체와 자식 항목을 연결 하는 데는 응용 프로그램 정의 값입니다.  
  
 `pszDelimiter`  
 [in] 주소는 끝의 스크립트 블록 구분 기호입니다. 구문 분석, 호스트 일반적으로 구분 기호 (예: 두 개의 작은따옴표), 스크립트 블록의 끝을 검색 사용 합니다.  
  
 구분 기호 전처리를 제공 하기 위해 엔진 작성 스크립트를 수 있습니다. 예를 들어, 엔진은 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표를 바꿀 수 있습니다. 엔진은 구분 기호로 사용 되는 방법을 결정 합니다.  
  
 구분 기호는 스크립트 블록의 끝을 표시 하지 않는 경우 NULL로 설정 합니다.  
  
 `ppse`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptEntry` 자식 인스턴스는 인터페이스입니다.  
  
 에 대 한 `IScriptNode` 웹 페이지를 나타내는 개체를이 매개 변수 반환는 `IScriptEntry` 스크립트 블록을 지정 하는 인스턴스입니다.  
  
 에 대 한 `IScriptEntry` 스크립트 블록을 나타내는 개체를이 매개 변수 반환는 `IScriptEntry` 함수 개체를 지정 하는 인스턴스가 있습니다.  
  
 에 대 한 `IScriptEntry` 함수를 나타내는 개체를 개체를이 메서드는 실패 합니다.  
  
 에 대 한 `IScriptScriptlet` 개체의 경우이 메서드는 실패 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 `IScriptNode` 웹 페이지 또는 요소 인터페이스를 나타냅니다. `IScriptEntry` 인터페이스 (에서 파생 된 `IScriptNode`) 스크립트 블록 또는 함수 개체를 나타냅니다. `IScriptScriptlet` 인터페이스 (에서 파생 된 `IScriptEntry`) 이벤트 처리기를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)
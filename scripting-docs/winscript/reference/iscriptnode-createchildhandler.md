---
title: IScriptNode::CreateChildHandler | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptNode.CreateChildHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::CreateChildHandler
ms.assetid: 4ce5eb10-1a3f-43b0-a4b7-599a397ed3a2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff2ba40d1570e23f0256bd34ca8aff0f8d77ce5c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnodecreatechildhandler"></a>IScriptNode::CreateChildHandler
자식 인스턴스로 스크립틀릿 추가 `IScriptNode`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateChildHandler(  
   LPCOLESTR          pszDefaultName,  
   LPCOLESTR          *prgpszNames,  
   ULONG              cpszNames,  
   LPCOLESTR          pszEvent,  
   LPCOLESTR          pszDelimiter,  
   ITypeInfo*         ptiSignature,  
   ULONG              iMethodSignature,  
   ULONG              isn,  
   DWORD              dwCookie,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszDefaultName`  
 [in] 주소는 스크립틀릿와 연결할 기본 이름입니다.  
  
 `prgpszNames`  
 [에 size_is (`cpszNames`)]는 호스트의 정규화 된 이름에서 식별자 목록입니다.  
  
 `cpszNames`  
 [in] 식별자의 수는 `prgpszNames` 매개 변수입니다.  
  
 `pszEvent`  
 [in] 스크립틀릿와 연결 된 이벤트 이름을 식별 하는 버퍼 주소입니다.  
  
 `pszDelimiter`  
 [in] 주소는 끝의 스크립트 블록 구분 기호입니다. 구문 분석, 호스트 일반적으로 구분 기호 (예: 두 개의 작은따옴표), 스크립트 블록의 끝을 검색 사용 합니다.  
  
 구분 기호 전처리 엔진을 제작 하는 스크립트에 있습니다. 예를 들어, 엔진은 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표를 바꿀 수 있습니다. 엔진은 구분 기호로 사용 되는 방법을 결정 합니다.  
  
 구분 기호는 스크립트 블록의 끝을 식별 하는 데 사용 되는 경우 NULL로 설정 합니다.  
  
 `ptiSignature`  
 [in] 함수 개체에 대 한 유형 정보입니다.  
  
 `iMethodSignature`  
 [in] 이 함수의 인덱스는 `ITypeInfo``ptiSignature` 매개 변수입니다.  
  
 `isn`  
 [in] 부모에서 자식 요소의 인덱스입니다.  
  
 `dwCookie`  
 [in] 호스트 개체와 해당 항목과 관련 하는 데 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ppse`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptEntry` 자식 인스턴스는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 스크립틀릿 이벤트 처리기를 지정합니다. 호출 되 면이 메서드는 스크립틀릿을 만듭니다는 `IScriptNode` 웹 페이지를 나타내는 개체입니다. 이 메서드는 다른 인터페이스에서 호출 되 면 성공 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)
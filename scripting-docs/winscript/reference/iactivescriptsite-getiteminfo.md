---
title: IActiveScriptSite::GetItemInfo | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptSite.GetItemInfo
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptSite_GetItemInfo
ms.assetid: f859ed3b-02c1-4924-99f8-5f5bf1bf8405
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ccb898c14571d1f1fd1fcae7cb0b9a6d322f2754
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitegetiteminfo"></a>IActiveScriptSite::GetItemInfo
스크립팅 엔진에 추가 된 항목에 대 한 정보를 얻을 수 있습니다는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetItemInfo(  
    LPCOLESTR pstrName,     // address of item name  
    DWORD dwReturnMask,     // bit mask for information retrieval  
    IUnknown **ppunkItem,   // address of pointer to item's IUnknown  
    ITypeInfo **ppTypeInfo  // address of pointer to item's ITypeInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrName`  
 [in] 에 지정 된 항목과 연결 된 이름에서 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
 `dwReturnMask`  
 [in] 반환 해야 하는 항목에 대 한 정보를 지정 하는 비트 마스크입니다. 스크립팅 엔진 때문에 최소한의 정보만 요청 해야 반환 매개 변수 중 일부 (예를 들어 `ITypeInfo`) 로드 하거나 생성 하는 데 상당한 시간이 걸릴 수 있습니다. 다음 값의 조합 될 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTINFO_IUNKNOWN|반환 된 `IUnknown` 이 항목에 대 한 인터페이스입니다.|  
|SCRIPTINFO_ITYPEINFO|반환 된 `ITypeInfo` 이 항목에 대 한 인터페이스입니다.|  
  
 `ppunkItem`  
 [out] 에 대 한 포인터를 받는 변수의 주소는 `IUnknown` 주어진 항목과 연결 된 인터페이스입니다. 스크립팅 엔진 צ ְ ײ는 `IUnknown::QueryInterface` 메서드는 `IDispatch` 항목에 대 한 인터페이스입니다. 이 매개 변수는 경우 NULL을 받습니다 `dwReturnMask` SCRIPTINFO_IUNKNOWN 가치를 포함 하지 않습니다. 항목 이름;에 연결 된 개체가 없는 경우 NULL 수신 하는 또한 이 메커니즘은 SCRIPTITEM_CODEONLY 플래그가 설정 지정된 된 항목이 추가 될 때 간단한 클래스를 만드는 데 사용 되는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
 `ppTypeInfo`  
 [out] 에 대 한 포인터를 받는 변수의 주소는 `ITypeInfo` 항목과 연결 된 인터페이스입니다. 이 매개 변수는 경우 NULL을 받습니다 `dwReturnMask` SCRIPTINFO_ITYPEINFO 값을 포함 하지 않는 형식 정보를이 항목에 대해 사용할 수 없는 경우 또는 합니다. 형식 정보를 사용할 수 없으면, 개체, 이벤트의 소스가 없습니다와 이름 바인딩을 실현 합니다 경우는 `IDispatch::GetIDsOfNames` 메서드. `ITypeInfo` 검색할 인터페이스 개체 다중 인터페이스 및 이벤트 인터페이스를 지원할 수 있습니다 (TKIND_COCLASS) 항목의 coclass에 설명 합니다. 항목에서 지 원하는 경우는 `IProvideMultipleTypeInfo` 인터페이스는 `ITypeInfo` 인터페이스 검색 인덱스 0과 같습니다 `ITypeInfo` 를 사용 하 여 가져올 것는 `IProvideMultipleTypeInfo::GetInfoOfIndex` 메서드.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`TYPE_E_ELEMENTNOTFOUND`|지정 된 이름의 항목을 찾을 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드를 가리키는 정보만 검색는 `dwReturnMask` 매개 변수; 성능이 향상 됩니다. 예를 들어 경우는 `ITypeInfo` 인터페이스 항목에 대 한 필요 하지 않은 단순히 지정 하지 않으면에 `dwReturnMask`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
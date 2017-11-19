---
title: IActiveScriptAuthor::AddNamedItem | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.AddNamedItem
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::AddNamedItem
ms.assetid: 951003b6-1c4a-4086-b7ce-2f128e007280
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 83d2597f8468bb97d20da655a56a751191ec4b55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthoraddnameditem"></a>IActiveScriptAuthor::AddNamedItem
엔진의 네임 스페이스를 제작 하는 스크립트에는 루트 수준 항목의 이름을 추가 합니다. A *루트 수준 항목* 은 개체의 속성 및 메서드가 포함 될 수 있는 이벤트 소스를 포함할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddNamedItem(  
   LPCOLESTR          pszName,  
   DWORD              dwFlags,  
   IDispatch          *pdisp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszName`  
 [in] 스크립트에서 볼 때 항목의 이름입니다. 이름은 고유 해야 하며 지속 합니다.  
  
 `dwFlags`  
 [in] 명명 된 항목에 연결 되어 있는 플래그입니다. 다음 값의 조합 될 수 있습니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|SCRIPTITEM_ISVISIBLE|0x00000002|스크립트의 네임 스페이스에서 사용할 수 있는 항목의 이름을 나타냅니다. 이 항목의 속성, 메서드 및 이벤트에는 액세스할 수 있습니다.<br /><br /> 규칙에 따라 항목의 속성 항목의 자식 멤버를 포함 합니다. 따라서 모든 자식 개체 속성 및 메서드 (및 해당 자식 멤버를 재귀적으로) 액세스할 수 있습니다.|  
|SCRIPTITEM_ISSOURCE|0x00000004|스크립트에서 스크립트 이벤트 처리기를 사용할 수 있도록 하는 항목 소스 이벤트를 나타냅니다.|  
|SCRIPTITEM_GLOBALMEMBERS|0x00000008|항목의 전역 속성 및 메서드는 스크립트와 연결 된 컬렉션 임을 나타냅니다. 해당 멤버는 전역 변수 및 방법으로 작성 됩니다.|  
|SCRIPTITEM_ISPERSISTENT|0x00000040|엔진을 제작 하는 스크립트를 저장 하는 항목을 저장할 수를 나타냅니다.|  
|SCRIPTITEM_CODEONLY|0x00000200|명명 된 항목은 코드 전용 개체를 나타내는 제작 하려면 멤버를 포함 하지 않는 있음을 나타냅니다.|  
|SCRIPTITEM_NOCODE|0x00000400|명명 된 항목을 추가, 이름만 작성 하는 전혀 있음을 나타냅니다.|  
  
 `pdisp`  
 [in] `IDispatch` 의 `NamedItem` 메서드, 속성 또는 이벤트 소스를 수집 하는 데 사용 되는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)
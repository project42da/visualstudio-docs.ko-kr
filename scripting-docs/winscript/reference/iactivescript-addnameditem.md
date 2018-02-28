---
title: IActiveScript::AddNamedItem | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScript.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- AddNamedItem method, IActiveScript interface
ms.assetid: a7c6317d-948f-4bb3-b169-1bbe5b7c7cc5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db65361e4bde14e803d9085a4530a505ccaf9fcb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptaddnameditem"></a>IActiveScript::AddNamedItem
스크립팅 엔진의 네임 스페이스에는 루트 수준 항목의 이름을 추가합니다. 루트 수준 항목은 속성 및 메서드, 이벤트 소스, 또는 세 가지 모두 있는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddNamedItem(  
    LPCOLESTR pstrName,  // address of item name  
    DWORD dwFlags          // item flags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrName`  
 [in] 스크립트에서 볼 때 항목의 이름을 포함 하는 버퍼의 주소입니다. 이름은 고유 해야 하며 지속 합니다.  
  
 `dwFlags`  
 [in] 항목에 연결 된 플래그입니다. 이러한 값의 조합 될 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTITEM_CODEONLY|명명 된 항목은 코드 전용 개체를 나타내는 나타내고 아니요에 `IUnknown` 이 코드 전용 개체와 연결 되도록 합니다. 호스트에이 개체에 대 한 이름만을 포함 합니다. C + +와 같은 개체 지향 언어에서이 플래그는 클래스를 만듭니다. 일부 언어는이 플래그를 지원합니다.|  
|SCRIPTITEM_GLOBALMEMBERS|항목의 전역 속성 및 메서드는 스크립트와 연결 된 컬렉션 임을 나타냅니다. 일반적으로 스크립팅 엔진 개체 이름을 무시 합니다 (아닌 다른 용도 대 한 쿠키로 사용 하는 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) 메서드, 또는 명시적 범위 지정을 확인 하기 위한)을 전역으로 멤버를 노출 하 고 변수 및 메서드를 제공 합니다. 따라서 호스트를 라이브러리를 확장 하는 (런타임 함수 및 등)는 스크립트에서 사용할 수 있습니다. 이름으로 처리 하기 위해 스크립팅 엔진에 두거나 충돌 (예를 들어 두 개의 SCRIPTITEM_GLOBALMEMBERS 항목이 있는 경우 동일한 이름의 메서드), 이러한 상황으로 인해 오류를 반환할 수는 있지만 합니다.|  
|SCRIPTITEM_ISPERSISTENT|스크립팅 엔진에 저장 된 경우에 항목을 저장할 수를 나타냅니다. 하지만 마찬가지로,이 플래그로 설정 초기화 된 상태로 다시 전환 (스크립팅 엔진 인터페이스 실제 개체에 대 한 모든 포인터를 해제, 해야) 항목의 이름 및 형식 정보를 유지 해야 합니다.|  
|SCRIPTITEM_ISSOURCE|항목 스크립트를 싱크할 수 있는 이벤트의 소스가 있는지를 나타냅니다. 자식 개체 (개체의 속성 개체 자체에 있는) 스크립트에는 이벤트 소스도 수 있습니다. 이 재귀, 하지만 컨트롤 컨테이너 및 포함 된 모든 구성원을 만드는 예를 들어 일반적인 경우에 대 한 편리한 메커니즘을 제공 합니다.|  
|SCRIPTITEM_ISVISIBLE|속성, 메서드 및 항목의 이벤트에 액세스할 수 있도록 스크립트의 네임 스페이스에서 사용할 수 있는 항목의 이름을 나타냅니다. 규칙에 따라 항목의 속성 포함 항목의 자식입니다. 따라서 모든 자식 개체 속성 및 메서드 (및 해당 자식 항목에 재귀적으로) 액세스할 수 있습니다.|  
|SCRIPTITEM_NOCODE|항목이 단순히 스크립트의 네임 스페이스에 추가 되 고 이름이 이며 하지 코드 연결 해야 하는 항목으로 처리할지를 나타냅니다. 예를 들어이 플래그를 설정 하지 않고 VBScript는 명명 된 항목에 대 한 별도 모듈 만들고 c + + 명명된 된 항목에 대 한 개별 래퍼 클래스를 만들 수 있습니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
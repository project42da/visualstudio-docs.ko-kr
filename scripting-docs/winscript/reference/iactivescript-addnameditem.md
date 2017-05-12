---
title: "IActiveScript::AddNamedItem | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.AddNamedItem
apilocation: scrobj.dll
helpviewer_keywords: 
  - "AddNamedItem 메서드, IActiveScript 인터페이스"
ms.assetid: a7c6317d-948f-4bb3-b169-1bbe5b7c7cc5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::AddNamedItem
루트 수준 항목의 이름을 스크립트 엔진의 이름 공간에 추가합니다.  루트 수준 항목 개체 속성 및 메서드, 이벤트 소스 또는 세입니다.  
  
## 구문  
  
```  
HRESULT AddNamedItem(  
    LPCOLESTR pstrName,  // address of item name  
    DWORD dwFlags          // item flags  
);  
```  
  
#### 매개 변수  
 `pstrName`  
 \[in\] 스크립트에서 볼 때 항목의 이름을 포함 하는 버퍼의 주소입니다.  이름이 고유 하 고 지속적인 이어야 합니다.  
  
 `dwFlags`  
 \[in\] 플래그를 항목에 연결 합니다.  이러한 값의 조합을 사용할 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|SCRIPTITEM\_CODEONLY|명명 된 항목 코드 전용 개체를 나타내며 호스트 없습니다 나타냅니다 `IUnknown` 이 코드 전용 객체에 연관 시킬 수 있습니다.  호스트에만이 개체의 이름이 있습니다.  C \+ \+과 같은 개체 지향 언어에서이 플래그는 클래스를 만듭니다.  이 플래그를 지원 하지 않는 언어도 있습니다.|  
|SCRIPTITEM\_GLOBALMEMBERS|항목 컬렉션의 전역 속성 및 스크립트와 연결 하는 방법입니다.  일반적으로 스크립팅 엔진 개체 이름을 무시 \(아닌 다른 목적으로 쿠키를 사용 하는 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) 메서드를 또는 명시적 범위를 확인 하기 위해\) 전역 변수 및 방법으로 해당 멤버를 노출 하 고.  이 호스트를 확장 라이브러리 \(런타임 함수와 등\) 스크립트에서 사용할 수 있습니다.  스크립팅 엔진 이름으로 처리 하기 위해 왼쪽 \(예를 들어, 두 SCRIPTITEM\_GLOBALMEMBERS 항목 메서드 이름이 같은 경우\) 때문에이 이런 오류가 반환 되지 않습니다 있지만, 충돌 합니다.|  
|SCRIPTITEM\_ISPERSISTENT|스크립팅 엔진에 저장 된 경우 항목은 저장할 수를 나타냅니다.  하지만이 플래그를 설정 합니다. 마찬가지로 나타냅니다 초기화 상태로 전환 \(스크립팅 엔진이 모든 실제 개체에서 인터페이스 포인터 해제 해야\) 항목의 이름 및 형식 정보를 유지 해야 합니다.|  
|SCRIPTITEM\_ISSOURCE|소스 스크립트를 싱크 하는 이벤트를 항목을 나타냅니다.  또한 자식 개체 \(개체는 자체의 개체의 속성\) 스크립트 이벤트의 소스가 있습니다.  편리한 메커니즘의 일반적인 경우, 예를 들어, 컨트롤 만드는 컨테이너와 모든 해당 멤버의 제공, 재귀 수 없습니다.|  
|SCRIPTITEM\_ISVISIBLE|항목의 이름을 사용할 수 있는 속성, 메서드 및 이벤트의 항목에 액세스할 수 있도록 하는 스크립트의 이름 공간에서입니다.  규칙에 따라 항목의 자식 항목의 속성을 포함합니다. 따라서 모든 자식 개체의 속성 및 메서드 \(및 자녀 들을 재귀적으로\)에 액세스할 수 있습니다.|  
|SCRIPTITEM\_NOCODE|항목 이름을 스크립트의 이름 공간에 추가 되 고 간단 하 게 코드에 연결 해야 하는 항목으로 처리 해야 나타냅니다.  예를 들어,이 플래그가 설정 되 고, 하지 않고 Vbscript에서 명명 된 항목에 대 한 별도 모듈을 만듭니다 및 C\+\+ 명명 된 항목에 대 한 별도 래퍼 클래스를 만들 수 있습니다.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
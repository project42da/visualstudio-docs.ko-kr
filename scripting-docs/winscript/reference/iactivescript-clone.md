---
title: "IActiveScript::Clone | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.Clone
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_Clone"
ms.assetid: aa000b2a-7085-448d-a422-f7adac7851cb
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::Clone
현재 스레드에서 없는 사이트는 로드 된 스크립팅 엔진에 반환 현재 스크립팅 엔진 \(현재 실행 상태\), 빼기를 복제 합니다.  이 새 스크립팅 엔진의 속성을 속성을 원래 스크립트 엔진에서 해당 된 전환 경우 초기화 상태로 됩니다 같습니다.  
  
## 구문  
  
```  
HRESULT Clone(  
    IActiveScript **ppscript  // receives pointer to IActiveScript  
);  
```  
  
#### 매개 변수  
 `ppscript`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 [IActiveScript](../../winscript/reference/iactivescript.md) 복제 된 스크립팅 엔진의 인터페이스.  호스트 사이트와 호출을 만들어야 합니다는 [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) 메서드는 초기화 상태로 될 때까지 새 스크립팅 엔진에, 따라서 사용할 수 있습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
  
## 설명  
 `IActiveScript::Clone` 메서드는 최적화 되어 `IPersist*::Save`, `CoCreateInstance`, 및 `IPersist*::Load`, 원래 스크립팅 엔진의 상태를 저장 하 고 새 스크립트 엔진으로 로드 된 경우 새 스크립팅 엔진의 상태를 같아야 합니다.  명명 된 항목을 복제 된 스크립팅 엔진에서 복제 된 있지만 각 항목에 대 한 특정 개체 포인터 기억 되 고 얻을 수 있는 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) 메서드.  이 동일한 개체 모델을을 사용할 스레드 진입점 \(아파트 모델\) 있습니다.  
  
 이 메서드는 여러 인스턴스를 동일한 스크립트를 실행할 수 있는 다중 스레드 서버 호스트에 대해 사용 됩니다.  스크립팅 엔진에 반환할 수 있습니다 `E_NOTIMPL`, 호스트 같은 결과 얻을 하 수 복제 상태를 유지 하 고 있는 스크립팅 엔진의 새 인스턴스를 만드는 경우에 `IPersist*` 인터페이스.  
  
 자료 설명선 호스트 개체 또는 결과 없이 비 기본 스레드에서이 메서드가 호출할 수 있는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
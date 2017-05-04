---
title: "IActiveScript::AddTypeLib | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.AddTypeLib
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_AddTypeLib"
ms.assetid: 8e507ea8-c80a-471c-b482-ae753c6e8595
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::AddTypeLib
형식 라이브러리를 스크립트에 대 한 이름 공간을 추가합니다.  이 유사 하 여 `#include` C\/C\+\+에서 지시문.  집합의 클래스 정의와 같은 미리 정의 된 항목 수 있도록 `typedefs`, 및 스크립트에 사용할 수 있는 런타임 환경에 추가할 상수 라는.  
  
## 구문  
  
```  
HRESULT AddTypeLib(  
    REFGUID guidTypeLib,  // CLSID of type library  
    DWORD dwMaj,          // major version number  
    DWORD dwMin,          // minor version number  
    DWORD dwFlags         // option flags  
);  
```  
  
#### 매개 변수  
 `guidTypeLib`  
 \[in\] CLSID 형식 라이브러리를 추가 합니다.  
  
 `dwMaj`  
 \[in\] 주 버전 번호입니다.  
  
 `dwMin`  
 \[in\] 부 버전 번호입니다.  
  
 `dwFlags`  
 \[in\] 옵션 플래그입니다.  다음과 같을 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|SCRIPTTYPELIB\_ISCONTROL|호스트에서 사용 하는 ActiveX 컨트롤 형식 라이브러리를 설명 합니다.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
|`TYPE_E_CANTLOADLIBRARY`|지정 된 형식 라이브러리를 로드할 수 없습니다.|  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
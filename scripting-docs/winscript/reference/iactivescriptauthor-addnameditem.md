---
title: "IActiveScriptAuthor::AddNamedItem | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.AddNamedItem
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::AddNamedItem"
ms.assetid: 951003b6-1c4a-4086-b7ce-2f128e007280
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# IActiveScriptAuthor::AddNamedItem
루트 수준 항목의 이름을 스크립트 제작 엔진의 네임 스페이스에 추가 합니다.  A  *루트 수준 항목* 메서드와 속성을 포함할 수 있고 고 수 이벤트 소스도 포함 하는 개체입니다.  
  
## 구문  
  
```  
HRESULT AddNamedItem(  
   LPCOLESTR          pszName,  
   DWORD              dwFlags,  
   IDispatch          *pdisp  
);  
```  
  
#### 매개 변수  
 `pszName`  
 \[in\] 스크립트에서 표시 되는 항목의 이름입니다.  이름이 고유 하 고 지속적인 이어야 합니다.  
  
 `dwFlags`  
 \[in\] 명명 된 항목에 연결 된 플래그입니다.  다음 값 조합이 될 수 있습니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|SCRIPTITEM\_ISVISIBLE|0x00000002|항목의 이름을 네임 스페이스를 스크립트에서 사용할 수 있음을 나타냅니다.  이 항목의 속성, 메서드 및 이벤트에 액세스할 수 있습니다.<br /><br /> 규칙에 따라 항목의 속성을 항목의 자식 멤버를 포함합니다.  따라서 모든 자식 개체의 속성 및 메서드 \(및 그 자식 멤버를 재귀적으로\)에 액세스할 수 있습니다.|  
|SCRIPTITEM\_ISSOURCE|0x00000004|항목 소스 이벤트 스크립트는 스크립트 이벤트 처리기가 있을 수 있음을 나타냅니다.|  
|SCRIPTITEM\_GLOBALMEMBERS|0x00000008|항목의 전역 속성 및 스크립트와 연결 된 메서드 컬렉션입니다.  멤버는 전역 변수와 메서드 이름으로 만들어집니다.|  
|SCRIPTITEM\_ISPERSISTENT|0x00000040|엔진을 제작 하는 스크립트를 저장 하는 경우 항목 저장할 수 없음을 나타냅니다.|  
|SCRIPTITEM\_CODEONLY|0x00000200|코드 전용 개체는 명명 된 항목을 나타내는 멤버를 작성할 수 없는 나타냅니다.|  
|SCRIPTITEM\_NOCODE|0x00000400|명명 된 항목 이름을 추가 하는 것 뿐 이며 제작에 아무가 나타냅니다.|  
  
 `pdisp`  
 \[in\] `IDispatch` 의 `NamedItem` 개체 메서드, 속성 또는 이벤트 소스에서 수집 하는 데 사용 됩니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)
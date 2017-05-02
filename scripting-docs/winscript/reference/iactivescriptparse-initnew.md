---
title: "IActiveScriptParse::InitNew | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptParse.InitNew
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptParse_InitNew"
ms.assetid: 3a582bd6-fc0d-43a5-812f-5ea55a8517a1
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptParse::InitNew
스크립팅 엔진을 초기화합니다.  
  
## 구문  
  
```  
HRESULT InitNew(void);  
```  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 초기화 중 오류가 발생 하는 경우.  
  
## 설명  
 스크립팅 엔진을 사용 하려면 다음 방법 중 하나 라고 합니다: `IPersist*::Load`, `IPersist*::InitNew`, 또는 `IActiveScriptParse::InitNew`.  이 방법의 의미와 동일 합니다 `IPersistStreamInit::InitNew`, 스크립팅 엔진 자체를 초기화 하려면이 메서드를 지시 한다는 점에서.  둘 다 호출할 수 없다는 점을 기억 `IPersist*::InitNew` 또는 `IActiveScriptParse::InitNew` 및 `IPersist*::Load`를 호출할 수 없습니다 `IPersist*::InitNew`, `IActiveScriptParse::InitNew`, 또는 `IPersist*::Load` 두 번 이상.  
  
## 참고 항목  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)
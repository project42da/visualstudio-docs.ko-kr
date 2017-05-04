---
title: "IActiveScriptAuthor::GetLanguageFlags | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.GetLanguageFlags
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::GetLanguageFlags"
ms.assetid: eb244452-62f7-4a73-b48f-1aa05cbcc32d
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# IActiveScriptAuthor::GetLanguageFlags
언어 정보를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetLanguageFlags(  
   DWORD              *pgrfasa  
);  
```  
  
#### 매개 변수  
 `pgrfasa`  
 \[out\] 언어 정보를 포함 하는 플래그입니다.  다음 값 조합이 될 수 있습니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|fasaPreferInternalHandler|0x0001|응용 프로그램 대신 엔진 제작 스크립트 스크립트 이벤트 처리기를 만드는 언어를 선호 합니다.|  
|fasaSupportInternalHandler|0x0002|엔진 제작 스크립트에 의해 생성 되는 스크립트 이벤트 처리기는 언어를 지원 합니다.|  
|fasaCaseSensitive|0x0004|스크립트 언어는 대\/소문자 구분입니다.|  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 엔진 제작 스크립트 이벤트 처리기를 관리 하는 경우 응용 프로그램을 호출 해야 `CreateChildHandler` 에서 `IScriptEntry` 개체입니다.  만든이 `IScriptScriptlet` 이벤트 처리기에 해당 하는 개체.  또한 엔진 스크립트 항목에 이벤트 처리기를 추가 합니다.  이벤트 처리기는 지정 된 서명 정보를 포함 하는 빈 함수입니다.  
  
 이벤트 처리기가 응용 프로그램을 관리 하는 경우 호출 해야 `CreateChildHandler` 에서 `IScriptNode` 이벤트 처리기 스크립트릿을 나타내는 개체입니다.  이렇게 작성 된 `IScriptScriptlet` 이벤트 처리기 스크립트릿와 연결 된 개체.  또한 응용 프로그램 이벤트로 빈 함수를 추가 해야 새 처리기 또는 기존 `IScriptEntry` 개체입니다.  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
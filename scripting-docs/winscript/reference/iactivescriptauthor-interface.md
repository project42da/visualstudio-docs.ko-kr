---
title: "IActiveScriptAuthor 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptAuthor 인터페이스"
ms.assetid: df1f454d-01ee-4beb-928b-48513d07365a
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# IActiveScriptAuthor 인터페이스
제작 IntelliSense 및 데이터 정렬 정보를 포함 하는 서비스를 나타냅니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IActiveScriptAuthor` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)|루트 수준 항목의 이름을 스크립트 제작 엔진의 네임 스페이스에 추가 합니다.  A  *루트 수준 항목* 메서드와 속성을 포함할 수 있고 고 수 이벤트 소스도 포함 하는 개체입니다.|  
|[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)|코드 스크립트릿 루트 수준 자식으로 추가 `IScriptNode` 개체입니다.  호스트에는 스크립트릿의 정규화 된 이름을 두 수준이 있을 수 있습니다.|  
|[IActiveScriptAuthor::AddTypeLib](../../winscript/reference/iactivescriptauthor-addtypelib.md)|형식 라이브러리의 네임 스페이스를 스크립트에 추가합니다.|  
|[IActiveScriptAuthor::GetChars](../../winscript/reference/iactivescriptauthor-getchars.md)|완성을 요청 된 컨텍스트에 대해 완료 문자 집합을 반환합니다.|  
|[IActiveScriptAuthor::GetEventHandler](../../winscript/reference/iactivescriptauthor-geteventhandler.md)|지정 된 특성을 가진 스크립트릿을 반환 합니다.|  
|[IActiveScriptAuthor::GetInfoFromContext](../../winscript/reference/iactivescriptauthor-getinfofromcontext.md)|반환 코드 블록에는 지정 된 문자에 대 한 앵커 위치 및 정보를 입력합니다.  IntelliSense, 전역 목록 및 매개 변수 팁 구성원에 대 한 정보를 제공합니다.|  
|[IActiveScriptAuthor::GetLanguageFlags](../../winscript/reference/iactivescriptauthor-getlanguageflags.md)|언어 정보를 반환합니다.|  
|[IActiveScriptAuthor::GetRoot](../../winscript/reference/iactivescriptauthor-getroot.md)|반환 된 `IScriptNode` 저자의 스크립트 트리의 루트입니다.|  
|[IActiveScriptAuthor::GetScriptletTextAttributes](../../winscript/reference/iactivescriptauthor-getscriptlettextattributes.md)|스크립트릿의 텍스트 특성을 반환합니다.|  
|[IActiveScriptAuthor::GetScriptTextAttributes](../../winscript/reference/iactivescriptauthor-getscripttextattributes.md)|스크립트 블록의 텍스트 특성을 반환합니다.|  
|[IActiveScriptAuthor::IsCommitChar](../../winscript/reference/iactivescriptauthor-iscommitchar.md)|응용 프로그램에서 지정 된 문자 문 완성 커밋 여부를 나타내는 값을 반환 합니다.|  
|[IActiveScriptAuthor::ParseScriptText](../../winscript/reference/iactivescriptauthor-parsescripttext.md)|스크립트 텍스트를 구문 분석 하 고 제작 스크립트 엔진을 제작 하는 텍스트 추가 만듭니다는 `IScriptEntry` 스크립트 블록에 해당 하는 개체입니다.|  
|[IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)|제거는 `NamedItem` 개체에서 네임 스페이스를 스크립트 엔진을 제작 합니다.|  
|[IActiveScriptAuthor::RemoveTypeLib](../../winscript/reference/iactivescriptauthor-removetypelib.md)|스크립트 제작 엔진 네임 스페이스에서 형식 라이브러리를 제거 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)
---
title: "Windows 스크립트 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4c750627-6797-4857-9f5e-e5f54371f83c
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Windows 스크립트 인터페이스
스크립팅을 추가 하려면 응용 프로그램 및 OLE 자동화를 통해 Microsoft Windows 스크립트 인터페이스를 제공 합니다.  스크립팅 호스트를 Windows 스크립트 기반의 스크립팅 엔진에 여러 개의 원본 및 공급 업체 관리 구성 요소 간에 스크립팅을 사용할 수 있습니다.  스크립트 자체의 구현\-언어, 구문, 영구적인 형식, 실행 모델 등에\-스크립트 공급 업체에 그대로 유지 됩니다.  
  
 Windows 스크립트 문서는 다음 단원으로 나뉩니다.  
  
 [Windows 스크립트 호스트](../winscript/windows-script-hosts.md)  
  
 [Windows 스크립트 엔진](../winscript/windows-script-engines.md)  
  
 [액티브 스크립트 디버깅 개요](../winscript/active-script-debugging-overview.md)  
  
 [액티브 스크립트 프로파일링 개요](../winscript/active-script-profiling-overview.md)  
  
 [Windows 스크립트 인터페이스 참조](../winscript/reference/windows-script-interfaces-reference.md)  
  
## Windows 스크립트 배경  
 라는 두 가지 범주로 Windows 스크립트 인터페이스: Windows 스크립트 호스트와 Windows 스크립트 엔진.  호스트 스크립팅 엔진을 만들고 스크립트를 실행 하는 엔진을 호출 합니다.  Windows 스크립트 호스트의 예로 다음과 같습니다.  
  
-   Microsoft Internet Explorer  
  
-   인터넷 도구를 제작 합니다.  
  
-   셸  
  
 모든 언어 또는 런타임 환경에 대 한 Windows 스크립트 엔진을 개발할 수 있습니다 포함:  
  
-   Microsoft Visual Basic Scripting Edition \(VBScript\)  
  
-   Perl  
  
-   Lisp  
  
 호스트 구현 최대한 융통성 있게 만들려면 Windows 스크립트에 대 한 OLE 자동화 래퍼를 제공 합니다.  그러나이 래퍼 개체 스크립팅 엔진을 인스턴스화하는 데 사용 하는 호스트의 런타임 이름 공간, 지 속성 모델 및 Windows 스크립트를 직접 사용 하는 경우에 그 것에 대 한 제어 정도 갖지 않습니다.  
  
 Windows 스크립트 디자인 \(예: 브라우저 및 뷰어\) nonauthoring 호스트와 스크립트 엔진 \(예: VBScript\) 경량 보관할 수 있습니다 하는 제작 환경에서 필요한 인터페이스 요소를 격리 합니다.  
  
## Windows 스크립트 기본 아키텍처  
 다음 그림에서는 Windows 스크립트 호스트는 Windows 스크립트 엔진 사이의 상호 작용을 보여 줍니다.  
  
 호스트와 엔진 간의 상호 작용에 관련 된 단계는 다음 목록에 지정 됩니다.  
  
1.  프로젝트를 만듭니다.  호스트 프로젝트 또는 문서를 로드합니다.  \(이 단계 Windows 스크립트에 특정 하지 않지만 여기에 완결성을 위해 포함 됩니다.\)  
  
2.  Windows 스크립트 엔진을 만듭니다.  호스트 호출 `CoCreateInstance` 새 Windows 스크립트 엔진을 만들려면 사용할 특정 스크립팅 엔진의 클래스 식별자 \(CLSID\)를 지정 합니다.  예를 들어, Internet Explorer HTML 브라우저 스크립팅 엔진의 클래스 식별자 CLSID 통해 수신 \= \<OBJECT\> html 특성 태그입니다.  
  
3.  스크립트를 로드 합니다.  스크립트 내용을 유지 되었을 경우, 호스트 스크립트 엔진이 호출 `IPersist*::Load` 스크립트 저장소, 스트림 또는 속성 모음을 공급 합니다.  호스트가 하나 그렇지 않은 경우 사용 하는 `IPersist*::InitNew` 또는 [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) null 스크립트를 작성 하는 방법.  텍스트를 사용할 수 있는 스크립트를 유지 관리 하는 호스트 [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md) 를 호출한 후 텍스트 스크립트, 스크립팅 엔진을 공급 `IActiveScriptParse::InitNew`.  
  
4.  명명 된 항목을 추가 합니다.  스크립팅 엔진의 이름 공간으로 가져온 각 최상위 명명 된 항목 \(예: 페이지 및 폼\), 호스트를 호출 하는 [IActiveScript::AddNamedItem](../winscript/reference/iactivescript-addnameditem.md) 엔진의 이름 공간에서 항목을 만들 수 있는 메서드.  이 단계는 명명 된 최상위 항목이 이미 영구 상태를 3 단계에서 로드 된 스크립트의 일부인 경우에 필요 하지 않습니다.  호스트는 사용 하지 않는 `IActiveScript::AddNamedItem` 하위 수준 명명 된 항목 \(예: 컨트롤을 HTML 페이지\);를 추가 하려면 대신 엔진 직접 하위 수준 항목에서 최상위 항목의 호스트를 사용 하 여 얻는 없습니다 `ITypeInfo` 및 `IDispatch` 인터페이스.  
  
5.  스크립트를 실행 합니다.  SCRIPTSTATE\_CONNECTED 플래그를 설정 하 여 스크립트를 실행 하려면 엔진 사용 하면 호스트는 [IActiveScript::SetScriptState](../winscript/reference/iactivescript-setscriptstate.md) 메서드.  이 호출 가능성이 정적 바인딩, \(아래 참조\), 이벤트 후크는 스크립팅된 유사 하 게에서 코드를 실행 등 모든 스크립팅 엔진 생성 작업을 수행 것 `main()` 함수입니다.  
  
6.  항목 정보를 가져옵니다.  스크립트 엔진이 기호 최상위 항목과 연결할 때마다 호출을 [IActiveScriptSite::GetItemInfo](../winscript/reference/iactivescriptsite-getiteminfo.md) 지정 된 항목에 대 한 정보를 반환 하는 메서드.  
  
7.  이벤트를 후크합니다.  실제 스크립트를 시작 하기 전에 스크립팅 엔진을 통해 모든 관련 개체의 이벤트를 연결 된 `IConnectionPoint` 인터페이스.  
  
8.  속성 및 메서드를 호출 합니다.  스크립트를 실행 하면 스크립팅 엔진 메서드 및 속성에 대 한 참조를 통해 명명 된 개체에서 인식 `IDispatch::Invoke` 또는 다른 표준 OLE 바인딩 메커니즘입니다.  
  
## Windows 스크립트 용어  
 이 목록은이 문서에 사용 된 스크립트와 관련 된 용어 정의 포함 합니다.  
  
|용어|정의|  
|--------|--------|  
|코드 개체|Visual Basic 폼과 관련 된 모듈 등 명명 된 항목을 연관 된 스크립팅 엔진에서 만든 인스턴스 또는 명명 된 항목에 연결 된 c \+ \+ 클래스.  가령,이 호스트 또는 다른 스크립트를 지원 하지 않는 엔터티 코드 개체를 조작할 수 있도록 OLE 자동화를 지 원하는 OLE 구성 요소 개체 모델 \(COM\) 개체입니다.|  
|명명 된 항목|OLE COM 개체 \(가령 한 OLE 자동화를 지 원하는\) 호스트 스크립트에 흥미로운 만하다는 것입니다.  HTML 페이지 및 브라우저에서 웹 브라우저, 문서 및 Microsoft word에서 대화 상자 등이 있습니다.|  
|스크립트|스크립팅 엔진에서 실행 되는 프로그램을 구성 하는 데이터입니다.  스크립트 블록의 텍스트를 포함 하는 연속 실행 데이터를 수 `pcode`, 심지어 컴퓨터 관련 실행 바이트 코드입니다.  스크립트 호스트 스크립팅 엔진 중 하나를 통해 로드는 `IPersist*` 인터페이스 또는 통과 [IActiveScriptParse](../winscript/reference/iactivescriptparse.md) 인터페이스.|  
|스크립팅 엔진|스크립트를 처리 하는 OLE 개체입니다.  스크립팅 엔진의 구현에서 [IActiveScript](../winscript/reference/iactivescript.md) 하 고 선택적으로 [IActiveScriptParse](../winscript/reference/iactivescriptparse.md) 인터페이스.|  
|스크립팅 호스트|응용 프로그램 또는 Windows 스크립트 엔진을 담당 하는 프로그램입니다.  호스트 구현에서 [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) 하 고 선택적으로 [IActiveScriptSiteWindow](../winscript/reference/iactivescriptsitewindow.md) 인터페이스.|  
|스크립트릿|통해 개체에 연결 된 스크립트의 일부를 [IActiveScriptParse](../winscript/reference/iactivescriptparse.md) 인터페이스.  집계 컬렉션 스크립틀릿의 스크립트입니다.|  
|스크립트 언어|스크립트 작성 \(예\)와 해당 언어의 의미는 언어입니다.|  
  
## 참고 항목  
 [Windows Script Interfaces](../winscript/windows-script-interfaces.md)
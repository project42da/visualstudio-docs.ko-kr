---
title: "IActiveScriptAuthor 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptAuthor interface
ms.assetid: df1f454d-01ee-4beb-928b-48513d07365a
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37abb356ab24d64a05a1f1209809d63e2f55e228
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthor-interface"></a>IActiveScriptAuthor 인터페이스
IntelliSense 및 데이터 정렬 정보를 포함 한 서비스를 작성을 나타냅니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptAuthor` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)|엔진의 네임 스페이스를 제작 하는 스크립트에는 루트 수준 항목의 이름을 추가 합니다. A *루트 수준 항목* 은 개체의 속성 및 메서드가 포함 될 수 있는 이벤트 소스를 포함할 수도 있습니다.|  
|[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)|루트 수준의 자식으로 추가 하는 코드 스크립틀릿 `IScriptNode` 개체입니다. 호스트는 스크립틀릿의 정규화 된 이름을 수준은 있을 수 있습니다.|  
|[IActiveScriptAuthor::AddTypeLib](../../winscript/reference/iactivescriptauthor-addtypelib.md)|스크립트에 대 한 네임 스페이스에 형식 라이브러리를 추가합니다.|  
|[IActiveScriptAuthor::GetChars](../../winscript/reference/iactivescriptauthor-getchars.md)|요청된 완료 컨텍스트에 대 한 완료 문자 집합을 반환합니다.|  
|[IActiveScriptAuthor::GetEventHandler](../../winscript/reference/iactivescriptauthor-geteventhandler.md)|지정 된 특성이 있는 스크립틀릿을 반환 합니다.|  
|[IActiveScriptAuthor::GetInfoFromContext](../../winscript/reference/iactivescriptauthor-getinfofromcontext.md)|반환 코드 블록에 지정 된 문자에 대 한 앵커 위치 및 정보를 입력합니다. IntelliSense, 전역 목록, 및 매개 변수 팁 멤버에 대 한 정보를 제공 합니다.|  
|[IActiveScriptAuthor::GetLanguageFlags](../../winscript/reference/iactivescriptauthor-getlanguageflags.md)|언어 정보를 반환합니다.|  
|[IActiveScriptAuthor::GetRoot](../../winscript/reference/iactivescriptauthor-getroot.md)|반환 된 `IScriptNode` 저자의 스크립트 트리의 루트입니다.|  
|[IActiveScriptAuthor::GetScriptletTextAttributes](../../winscript/reference/iactivescriptauthor-getscriptlettextattributes.md)|스크립틀릿의 텍스트 특성을 반환 합니다.|  
|[IActiveScriptAuthor::GetScriptTextAttributes](../../winscript/reference/iactivescriptauthor-getscripttextattributes.md)|스크립트 블록의 텍스트 특성을 반환합니다.|  
|[IActiveScriptAuthor::IsCommitChar](../../winscript/reference/iactivescriptauthor-iscommitchar.md)|지정 된 문자 응용 프로그램에서 문 완성 커밋 해야 하는지 여부를 나타내는 값을 반환 합니다.|  
|[IActiveScriptAuthor::ParseScriptText](../../winscript/reference/iactivescriptauthor-parsescripttext.md)|스크립트 텍스트를 구문 분석 엔진을 제작 하는 제작 스크립트에 텍스트를 추가 하 고 만듭니다는 `IScriptEntry` 스크립트 블록에 해당 하는 개체입니다.|  
|[IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)|제거는 `NamedItem` 엔진을 제작 하는 스크립트의 네임 스페이스에서 개체입니다.|  
|[IActiveScriptAuthor::RemoveTypeLib](../../winscript/reference/iactivescriptauthor-removetypelib.md)|엔진 네임 스페이스를 제작 하는 스크립트에서 형식 라이브러리를 제거 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)
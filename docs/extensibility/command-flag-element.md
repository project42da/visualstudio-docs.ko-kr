---
title: "명령 플래그 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CommandFlag 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, CommandFlag"
ms.assetid: 5ef63399-d2db-4dc1-97ce-be1bd4ef4e39
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 명령 플래그 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

부모 요소를 수정합니다.  
  
## 구문  
  
```  
<CommandFlag>DynamicVisibility</CommandFlag>  
```  
  
## 특성 및 요소  
 다음 섹션에서는 유효한 요소 값입니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|값|설명|  
|-------|--------|  
|AllowParams|사용자가 명령 매개 변수를 입력할 수 있는 나타냅니다는 **명령** 명령의 정식 이름을 입력할 때 창입니다.<br /><br /> 유효 기간: `Button`|  
|AlwaysCreate|메뉴 그룹 또는 단추 없는 경우에 만들어집니다.<br /><br /> 유효 기간: `Menu`|  
|CaseSensitive|사용자 항목 대\/소문자를 구분 하지 않습니다.<br /><br /> 유효 기간: `Combo`|  
|CommandWellOnly|최상위 메뉴에서 명령 표시 되지 않으며 바로 가기 키에 바인딩에 대 한 추가 셸 사용자 지정, 예를 들어에 사용할 수 있게 하려는 경우에이 플래그를 적용 합니다. VSPackage를 설치한 후 열고이 명령은 사용자를 지정할 수 있습니다는 **옵션** 다음 아래 명령 배치를 편집 하 고 대화 상자는 **키보드 환경** 범주입니다. 이 플래그는 바로 가기 메뉴, 도구 모음, 메뉴 컨트롤러 또는 하위 메뉴에서 배치 영향을 주지 않습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|DefaultDisabled|기본적으로 명령이 비활성화 되어 있는 것을 구현 하는 VSPackage가 로드 되지 않은 경우 또는 `QueryStatus` 메서드가 호출 되지 않았습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|DefaultDocked|기본적으로 도킹 합니다. 항상 컨트롤이 도킹 된 도구 모음 적용이 더 이상 설정 합니다.|  
|DefaultInvisible|기본적으로이 명령은 보이지 않으면 구현 하는 VSPackage가 로드 되지 않은 경우 또는 `QueryStatus` 메서드가 호출 되지 않았습니다.<br /><br /> 이를 결합 하는 것이 좋습니다는 `DynamicVisibility` 플래그입니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|DontCache|개발 환경 캐시 하지 않고는 `QueryStatus` 이 명령에 대 한 메서드 결과입니다.<br /><br /> 메뉴의 경우에이 해당 메뉴 항목의 텍스트를 캐시할 필요가 메뉴 컨트롤러를 나타냅니다. 메뉴에는 동적 항목 또는 동적 텍스트를 포함 된 항목을 포함 하는 경우이 플래그를 사용 합니다.<br /><br /> 에 대 한 유효한: `Button`, `Menu`|  
|DynamicItemStart|동적 목록 시작 부분을 나타냅니다. 이렇게 하면 연속적으로 호출 하 여 목록을 작성 하는 환경을 `QueryStatus` OLECMDERR\_E\_UNSUPPORTED 플래그 반환 될 때까지 목록 항목에 대 한 메서드. 이 위치 가장 최근에 사용 된 같은 \(MRU\) 및 창 목록 항목에 대 한 잘 작동 합니다.<br /><br /> 유효 기간: `Button`|  
|DynamicVisibility|통해 명령의 표시 유형을 변경할 수는 `QueryStatus` 메서드 또는 컨텍스트에 포함 된 GUID 통해는 `VisibilityConstraints` 섹션입니다.<br /><br /> 주 창에 표시 되는 최상위 도구 모음에는 없지만 메뉴 및 도구 창 도구 모음에서 표시 되는 명령에 적용 됩니다. 최상위 도구 모음 항목 비활성화 수 있지만 숨겨져 있지 않으면이 OLECMDF\_INVISIBLE 플래그에서 반환 되는 수 고 `QueryStatus` 메서드. 도구 창 도구 모음에 나타나는 도구 모음 명령이 숨길 수 있습니다.<br /><br /> 메뉴에서이 플래그도 것 해야 자동으로 숨김을 나타냅니다 모든 해당 멤버를 숨기면 됩니다. 최상위 메뉴에 이미이 문제 때문에이 플래그는 일반적으로 하위 메뉴에 할당 됩니다.<br /><br /> 이 플래그를 결합할 수는 `DefaultInvisible` 플래그입니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|필터 키|아래에서 필터링 하는 키 항목을 참조 하십시오 [콤보 요소](../extensibility/combo-element.md)합니다.<br /><br /> 유효 기간: `Combo`|  
|FixMenuController|이 명령은 기본적으로 항상 메뉴 컨트롤러가이 명령은 배치 되 면 즉, 자체 메뉴 컨트롤러 단추를 선택할 때마다 명령을 선택 합니다. 에 메뉴 컨트롤러는 `TextIsAnchorCommand` 메뉴 컨트롤러는 또한 있는 명령에서 해당 텍스트를 사용 하며 다음 플래그가 설정는 `FixMenuController` 플래그입니다.<br /><br /> 메뉴 컨트롤러에서 명령을 하나만 있어야는 `FixMenuController` 플래그입니다. 둘 이상의 명령으로 표시 되므로 경우 메뉴에서 마지막 명령이 기본 명령으로 바뀝니다.<br /><br /> 유효 기간: `Button`|  
|IconAndText|메뉴 및 도구 모음에 프로그램 아이콘 및 텍스트를 표시 합니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|NoAutoComplete|자동 완성 기능이 비활성화 됩니다.<br /><br /> 유효 기간: `Combo`|  
|NoButtonCustomize|이 단추를 사용자 지정 사용자를 수 없습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|NoKeyCustomize|사용자 지정 키보드를 사용 하지 마십시오.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|NoShowOnMenuController|이 명령은 메뉴 컨트롤러에 커서가, 명령 드롭 다운 목록에 나타나지 않습니다.<br /><br /> 유효 기간: `Button`|  
|NotInTBList|사용 가능한 도구 모음 목록에 나타나지 않습니다. 도구 모음 메뉴 형식에 대해서만 유효합니다.<br /><br /> 유효 기간: `Menu`|  
|NoToolbarClose|사용자는 도구 모음을 닫을 수 없습니다. 도구 모음 메뉴 형식에 대해서만 유효합니다.<br /><br /> 유효 기간: `Menu`|  
|Pict|도구 모음에서 있지만 메뉴에만 텍스트에만 아이콘을 표시 합니다. 아이콘이 없는 지정 된 경우 도구 모음에서 클릭할 수 있는 빈 공간을 보여 줍니다.<br /><br /> 유효 기간: `Button`|  
|PostExec|명령에서 비블로킹 만듭니다. 모든 사전 처리 쿼리가 완료 될 때까지 실행을 지연 하는 개발 환경.<br /><br /> 유효 기간: `Button`|  
|RouteToDocs|이 명령은 현재 문서에 라우팅됩니다.<br /><br /> 유효 기간: `Button`|  
|StretchHorizontally|이 플래그를 설정 하는 경우 너비 콤보 상자에 대 한 최소 너비 바뀌고 콤보 상자 확장을 사용 가능한 공간을 채우는 도구 모음에 공간이 있으면 됩니다. 이 도구 모음, 도킹 가로로 및 하나의 콤보 상자 도구 모음에 있습니다 \(첫 번째 콤보 상자를 제외한 모든 플래그는 무시 됨\) 플래그를 사용 하 여 경우에 발생 합니다.<br /><br /> 유효 기간: `Combo`|  
|TextMenuUseButton|사용 하 여 `ButtonText` 메뉴에 대 한 필드입니다. 기본 필드는 `MenuText` 지정 된 경우.<br /><br /> 유효 기간: `Button`|  
|TextChanges|명령이 나 메뉴 텍스트를 변경할 수 런타임 시 일반적으로 통해는 `QueryStatus` 메서드.<br /><br /> 에 대 한 유효한: `Button`, `Menu`|  
|TextChangesButton|유효 기간: `Button`|  
|TextIsAnchorCommand|메뉴 컨트롤러에 대해서는 메뉴의 텍스트 \(앵커\) 기본 명령에서 가져옵니다. 앵커 명령을 선택 하거나 래치 마지막 명령이입니다. 이 플래그가 설정 되지 않은 경우 메뉴 컨트롤러 사용 하는 자체 `MenuText` 필드입니다. 그러나 해당 컨트롤러에서 마지막 선택한 명령을 활성화 여전히 메뉴 컨트롤러를 클릭 합니다.<br /><br /> 이 플래그를 결합 하는 것이 좋습니다는 `TextChanges` 플래그입니다.<br /><br /> 이 플래그는 MenuController 또는 MenuControllerLatched 유형의 메뉴에만 적용 됩니다.<br /><br /> 유효 기간: `Menu`|  
|TextMenuCtrlUseMenu|사용 된 `MenuText` 필드 메뉴 컨트롤러에 있습니다. 기본 필드는 `ButtonText`합니다.<br /><br /> 유효 기간: `Button`|  
|TextMenuUseButton|사용 하 여 `ButtonText` 메뉴에 대 한 필드입니다. 기본 필드는 `MenuText` 지정 된 경우.<br /><br /> 유효 기간: `Button`|  
|TextOnly|아이콘을 지정 하는 경우에 도구 모음 또는 메뉴 아이콘 없음에 텍스트를 표시 합니다.<br /><br /> 유효 기간: `Button`|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[단추 요소](../extensibility/buttons-element.md)|에 대 한 그룹이 제공 [Button 요소](../extensibility/button-element.md) 요소입니다.|  
|[메뉴 요소](../extensibility/menus-element.md)|VSPackage를 구현 하는 모든 메뉴를 정의 합니다.|  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
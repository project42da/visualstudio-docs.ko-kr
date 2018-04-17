---
title: 명령 플래그 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CommandFlag element (VSCT XML schema)
- VSCT XML schema elements, CommandFlag
ms.assetid: 5ef63399-d2db-4dc1-97ce-be1bd4ef4e39
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 036b9658957b76b62e3a9b44b59e07700f276a32
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="command-flag-element"></a>명령 플래그 요소
부모 요소를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<CommandFlag>DynamicVisibility</CommandFlag>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에 잘못 된 요소 값에 설명 합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|값|설명|  
|-----------|-----------------|  
|AllowParams|사용자가에 명령 매개 변수를 입력할 수 나타냅니다는 **명령** 명령이의 정식 이름을 입력할 때 창.<br /><br /> 에 대해 유효 합니다. `Button`|  
|AlwaysCreate|메뉴 단추 또는 그룹이 아니면 경우에 만들어집니다.<br /><br /> 에 대해 유효 합니다. `Menu`|  
|CaseSensitive|사용자 항목 대/소문자를 구분 하지 않습니다.<br /><br /> 에 대해 유효 합니다. `Combo`|  
|CommandWellOnly|최상위 메뉴에는 명령이 표시 되지 않는 하 고 바로 가기 키에 바인딩 추가 셸 사용자 지정, 예를 들어 사용할 수 있도록 하려는 경우이 플래그를 적용 합니다. VSPackage를 설치한 후를 열어 이러한 명령은 사용자를 지정할 수 있습니다는 **옵션** 대화 상자에서 명령 배치를 편집 하 고는 **키보드 환경** 범주입니다. 이 플래그는 바로 가기 메뉴, 도구 모음, 메뉴 컨트롤러 또는 하위 메뉴에서 배치 영향을 주지 않습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|DefaultDisabled|명령을 구현 하는 VSPackage를 로드 되지 않은 경우 기본적으로 비활성화 또는 `QueryStatus` 메서드가 호출 되지 않았습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|DefaultDocked|기본적으로 도킹 합니다. 항상으로 도킹 된 도구 모음 적용이 더 이상 설정 합니다.|  
|DefaultInvisible|기본적으로이 명령은 보이지 않으면 구현 하는 VSPackage를 로드 되지 않은 경우 또는 `QueryStatus` 메서드가 호출 되지 않았습니다.<br /><br /> 이를 결합 하는 것이 좋습니다는 `DynamicVisibility` 플래그입니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|DontCache|개발 환경 캐시 하지 않습니다는 `QueryStatus` 이 명령에 대 한 메서드 결과입니다.<br /><br /> 메뉴에서이 해당 메뉴 항목의 텍스트를 캐시 하지 않아야 메뉴 컨트롤러를 나타냅니다. 동적 항목 또는 동적 텍스트가 있는 항목의 메뉴에 포함 되어 있는 경우이 플래그를 사용 합니다.<br /><br /> 에 대 한 유효한: `Button`, `Menu`|  
|DynamicItemStart|동적 목록의 시작 부분을 나타냅니다. 이 연속적으로 호출 하 여 목록을 작성 환경을 통해는 `QueryStatus` OLECMDERR_E_UNSUPPORTED 플래그 반환 될 때까지 목록 항목에는 메서드. 가장 최근에 사용 된 같은 (MRU) 목록 및 창 목록 항목에 대 한 효과적입니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|DynamicVisibility|통해 명령의 표시 유형을 변경할 수는 `QueryStatus` 메서드 또는 컨텍스트에 포함 된 GUID 통해는 `VisibilityConstraints` 섹션.<br /><br /> 주 창에 표시 되는 최상위 도구 모음에는 없지만 메뉴 및 도구 창 도구 모음에서 표시 되는 명령에 적용 됩니다. 최상위 도구 모음 항목을 사용 하지 않지만 숨겨져 있지 않으면이 OLECMDF_INVISIBLE 플래그에서 반환 되 면 수는 `QueryStatus` 메서드. 도구 창 도구 모음에 나타나는 도구 모음 명령이 숨길 수 있습니다.<br /><br /> 메뉴에서이 플래그도 것 해야 자동으로 숨김을 나타냅니다 모든 해당 멤버 숨겨져 있습니다. 최상위 메뉴에 이미이 동작은 있기 때문에이 플래그는 일반적으로 하위 메뉴에 할당 됩니다.<br /><br /> 이 플래그와 함께 사용할 해야는 `DefaultInvisible` 플래그입니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|필터 키|아래에서 필터링 하는 키 항목을 참조 [콤보 요소](../extensibility/combo-element.md)합니다.<br /><br /> 에 대해 유효 합니다. `Combo`|  
|FixMenuController|이 명령은 기본적으로 항상 메뉴 컨트롤러 등이 명령은 있을 경우 즉,이 명령은 자체 메뉴 컨트롤러 단추 선택 될 때마다 선택 되어 있습니다. 메뉴 컨트롤러에는 `TextIsAnchorCommand` 플래그가 설정, 다음 메뉴 컨트롤러에도 해당 텍스트가 있는 명령에서 소요 되는 `FixMenuController` 플래그입니다.<br /><br /> 메뉴 컨트롤러에서 명령을 하나만 있어야는 `FixMenuController` 플래그입니다. 둘 이상의 명령으로 표시 하므로 기본 명령 메뉴의 마지막 명령이 됩니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|IconAndText|메뉴 및 도구 모음에 텍스트를 표시 합니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`, `Menu`|  
|NoAutoComplete|자동 완성 기능을 사용 하는 사용할 수 없습니다.<br /><br /> 에 대해 유효 합니다. `Combo`|  
|NoButtonCustomize|이 단추를 사용자 지정 사용자를 수 없습니다.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|NoKeyCustomize|사용자 지정 키보드를 사용 하지 마십시오.<br /><br /> 에 대 한 유효한: `Button`, `Combo`|  
|NoShowOnMenuController|이 명령은 등 메뉴 컨트롤러에 있을 경우이 명령은 드롭 다운 목록에 나타나지 않습니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|NotInTBList|사용 가능한 도구 모음 목록에 나타나지 않습니다. 도구 모음 메뉴 형식에 대해서만 유효합니다.<br /><br /> 에 대해 유효 합니다. `Menu`|  
|NoToolbarClose|사용자는 도구 모음을 닫을 수 없습니다. 도구 모음 메뉴 형식에 대해서만 유효합니다.<br /><br /> 에 대해 유효 합니다. `Menu`|  
|Pict|도구 모음에서 하지만 메뉴에만 텍스트에만 아이콘을 표시 합니다. 아이콘이 없는 지정 된 경우 도구 모음에 클릭 가능한 빈 공간을 보여 줍니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|PostExec|명령에서 비블로킹 만듭니다. 모든 사전 처리 쿼리가 완료 될 때까지 실행을 지연 하는 개발 환경입니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|RouteToDocs|이 명령은 현재 문서에 라우팅됩니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|StretchHorizontally|이 플래그를 설정 하는 경우 너비 콤보 상자에 대 한 최소 너비 되며 콤보 상자의 사용 가능한 공간을 채우기 위해 늘여 도구 모음에서 공간이 있는 경우. 도구 모음 도킹 가로로, 도구 모음에서 하나의 콤보 상자 (플래그는 첫 번째 콤보 상자 제외한 모든 페이지에서 무시 됩니다.) 플래그를 사용할 수 있고 경우에 발생 합니다.<br /><br /> 에 대해 유효 합니다. `Combo`|  
|TextMenuUseButton|사용 하 여 `ButtonText` 메뉴에 대 한 필드입니다. 기본 필드는 `MenuText` 지정 된 경우.<br /><br /> 에 대해 유효 합니다. `Button`|  
|TextChanges|명령이 나 메뉴 텍스트도 통해 일반적으로 런타임 시 변경할 수 있습니다는 `QueryStatus` 메서드.<br /><br /> 에 대 한 유효한: `Button`, `Menu`|  
|TextChangesButton|에 대해 유효 합니다. `Button`|  
|TextIsAnchorCommand|메뉴 컨트롤러에 대 한 메뉴의 텍스트 기본 (앵커) 명령에서 가져옵니다. 앵커 명령을 선택 하거나 래치 마지막 명령이입니다. 이 플래그를 설정 하지 않으면, 메뉴 컨트롤러 사용 하는 자체 `MenuText` 필드입니다. 반면, 메뉴 컨트롤러를 클릭 하면 사용할 수 해당 컨트롤러에서 마지막 선택한 명령입니다.<br /><br /> 이 플래그를 결합 하는 것이 좋습니다는 `TextChanges` 플래그입니다.<br /><br /> 이 플래그는 MenuController 또는 MenuControllerLatched 메뉴 형식에 적용 됩니다.<br /><br /> 에 대해 유효 합니다. `Menu`|  
|TextMenuCtrlUseMenu|사용 된 `MenuText` 필드에 메뉴 컨트롤러입니다. 기본 필드는 `ButtonText`합니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
|TextMenuUseButton|사용 하 여 `ButtonText` 메뉴에 대 한 필드입니다. 기본 필드는 `MenuText` 지정 된 경우.<br /><br /> 에 대해 유효 합니다. `Button`|  
|TextOnly|아이콘 파일이 지정 하는 경우에 도구 모음 또는 메뉴 아이콘 없음만 텍스트를 표시 합니다.<br /><br /> 에 대해 유효 합니다. `Button`|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Buttons 요소](../extensibility/buttons-element.md)|에 대 한 그룹이 제공 [Button 요소](../extensibility/button-element.md) 요소입니다.|  
|[Menus 요소](../extensibility/menus-element.md)|VSPackage 구현 하는 모든 메뉴를 정의 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
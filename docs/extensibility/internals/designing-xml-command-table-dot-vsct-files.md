---
title: "XML 명령 테이블 디자인 (합니다. Vsct) 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT files, designing
ms.assetid: bb87a322-bac4-4258-92bc-9a876f05d653
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fcb8533dda001d447fd10fcb69b3cccd6d2d91a1
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="designing-xml-command-table-vsct-files"></a>XML 명령 테이블 디자인 (합니다. Vsct) 파일
레이아웃 및 VSPackage에 대 한 명령 항목의 모양을 XML 명령 테이블 (.vsct) 파일에 설명합니다. 명령 항목 단추, 콤보 상자, 메뉴, 도구 모음 및 명령 항목 그룹에 포함 됩니다. 이 항목에서는 XML 명령 테이블 파일에 미치는 영향 명령 항목 및 메뉴, 및를 만드는 방법을 설명 합니다.

## <a name="commands-menus-groups-and-the-vsct-file"></a>명령, 메뉴, 그룹 및.vsct 파일
 .vsct 파일 명령, 메뉴, 명령 그룹 주위에 구성 됩니다. .Vsct 파일에서 XML 태그에는 각 명령 단추, 명령 배치 비트맵 등 다른 관련된 항목과 함께 이러한 항목을 나타냅니다.

 실행 하 여 새 VSPackage를 만들 때의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 템플릿을 템플릿은 메뉴 명령, 도구 창 또는 선택 항목에 따라 사용자 지정 편집기에 대 한 필요한 요소와.vsct 파일을 생성 합니다. 이.vsct 파일 특정 VSPackage의 요구 사항에 맞게 수정할 수 있습니다. .Vsct 파일을 수정 하는 방법의 예의 예제를 참조에 대 한 [확장 메뉴 및 명령을](../../extensibility/extending-menus-and-commands.md)합니다.

 새, 빈.vsct 파일을 만들려면 참조 [하는 방법: 만들기는 합니다. Vsct 파일](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)합니다. 를 만든 후 명령 항목 레이아웃을 설명 하기 위해 파일에 XML 요소, 특성 및 값 추가 합니다. 자세한 XML 스키마를 참조 하십시오.는 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)합니다.

## <a name="differences-between-ctc-and-vsct-files"></a>.Ctc 및.vsct 파일 간의 차이점
 에 이제.ctc 파일 형식을 더 이상 사용 되지.vsct 파일에서 XML 태그 있으며의 의미는 동일, 해당 구현에 약간 차이가 있습니다.

-   새  **\<extern >** 태그는 다른.h 파일을 같은 컴파일하도록 참조할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 도구 모음입니다.

-   .Vsct 파일 지원 하는 동안는 **/include** 문,.ctc 파일 에서처럼 갖추고 새 \< **가져올 >** 요소입니다. 차이점은 **포함 /** 는에서 **모든** 정보의 하지만 \< **가져올 >** 이름만에 제공 합니다.

-   .Ctc 파일 필요 하면 전처리기 지시문을 정의 하는 헤더 파일에 하나에 필요 하지 않습니다.vsct 파일입니다. 대신 프로그램 지시문에 있는 기호 테이블에 추가할는  **\<기호 >** .vsct 파일의 아래쪽에 있는 요소입니다.

-   .vsct 파일 기능은  **\<주석 >** 태그에 메모나 그림도 같은 정보를 포함할 수 있습니다.

-   값은 항목에는 특성으로 저장 됩니다.

-   명령 플래그를 개별적으로 저장 하거나 누적 될 수 있습니다.  그러나 IntelliSense,에서 작동 하지 않습니다 누적된 명령 플래그입니다. 명령 플래그에 대 한 자세한 내용은 참조는 [명령 플래그 요소](../../extensibility/command-flag-element.md)합니다.

-   분할의 드롭다운 목록, 바로 가기 단축키 + 등과 같은 여러 형식을 지정할 수 있습니다.

-   Guid의 유효성을 검사 하지 않습니다.

-   각 UI 요소에 함께 표시 되는 텍스트를 나타내는 문자열입니다.

-   부모는 선택 사항입니다. 생략 하는 경우 "알 수 없는 그룹" 값이 사용 됩니다.

-   아이콘 인수는 선택 사항입니다.

-   .ctc 동일 비트맵 섹션-파일을 제외 하 고는 가져올 vsct.exe 컴파일러에서 컴파일 타임에 href 통해 파일 이름을 지정할 수 있습니다.

-   ResID-이전 비트맵 리소스 ID 사용할 수 있으며 여전히 동일한.ctc 파일에서와 같이 작동 합니다.

-   HRef-하는 새 메서드 비트맵 리소스에 대 한 파일 이름을 지정할 수 있습니다. 사용 하는 섹션을 생략할 수 있으므로 대부분이 사용 됩니다 가정 합니다. 컴파일러는 먼저 모든 네트워크 공유에서 파일에 대 한 로컬 리소스 및 /I 스위치에 의해 정의 된 모든 리소스에 대 한 검색 됩니다.

-   Keybinding-더 이상 에뮬레이터를 지정할 수 있어야 합니다. 하나를 지정 않으면, 컴파일러는 편집기 및 에뮬레이터 동일 합니다.

-   Keychord-삭제 되었습니다. 새 형식은 Key1, Mod1, Key2 Mod2입니다.  문자, 16 진수 또는 VK 상수를 지정할 수 있습니다.

 새 컴파일러, vsct.exe,.ctc와.vsct 파일을 컴파일합니다. 그러나 이전 ctc.exe 컴파일러 됩니다 인식 지도.vsct 파일을 컴파일합니다.

 Vsct.exe 컴파일러를 사용 하 여.vsct 파일에 기존.cto 파일을 변환할 수 있습니다. 이 대 한 자세한 내용은 참조 [하는 방법: 만들기는 합니다. 기존 Vsct 파일입니다. Cto 파일](../../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file)합니다.

## <a name="the-vsct-file-elements"></a>.Vsct 파일 요소
 명령 테이블에는 다음 계층 구조 및 요소에 있습니다.

 [CommandTable 요소](../../extensibility/commandtable-element.md) -모든 명령, 메뉴 그룹 및 VSPackage와 연결 된 메뉴를 나타냅니다.

 [Extern 요소](../../extensibility/extern-element.md) -.vsct 파일에 병합 하려는 모든 외부.h 파일을 참조 합니다.

 [요소를 포함](../../extensibility/include-element.md) -your.vsct 파일과 함께 컴파일하는 데 사용할 모든 추가 헤더 (.h) 파일을 참조 합니다. .Vsct 파일을 정의 하는 명령, 메뉴 그룹 메뉴는 IDE 또는 다른 VSPackage에서 제공 하는 상수를 포함 하는.h 파일을 포함할 수 있습니다.

 [요소를 명령](../../extensibility/commands-element.md) -모든 실행 될 수 있는 개별 명령을 나타냅니다. 각 명령에는 다음과 같은 4 명의 하위 요소가 있습니다.

 [메뉴 요소](../../extensibility/menus-element.md) -모든 메뉴와 VSPackage에서 도구 모음을 나타냅니다. 메뉴는 명령 그룹에 대 한 컨테이너입니다.

 [Groups 요소](../../extensibility/groups-element.md) -모든 VSPackage에서 그룹을 나타냅니다. 그룹은 컬렉션의 개별 명령 합니다.

 [요소는 단추](../../extensibility/buttons-element.md) -모든 명령 단추와 VSPackage에서 메뉴 항목을 나타냅니다. 단추는 명령에 연결 될 수 있는 시각적 컨트롤입니다.

 [비트맵 요소](../../extensibility/bitmaps-element.md) -모든 모든 VSPackage에서 단추에 대 한 비트맵을 나타냅니다. 비트맵은 컨텍스트에 따라 명령 단추를에서 또는 옆에 표시 되는 그림입니다.

 [CommandPlacements 요소](../../extensibility/commandplacements-element.md) — VSPackage의 메뉴에는 각 명령을 해야 위치할 추가 위치를 나타냅니다.

 [VisibilityConstraints 요소](../../extensibility/visibilityconstraints-element.md) -명령을 표시 여부 전혀 시간, 또는 특정 대화 상자 또는 창 표시 되 면 같은 특정 컨텍스트에서 지정 합니다. 메뉴 및 명령을이 요소에 대 한 값이 있는 지정된 된 컨텍스트 활성화 되어 있는 경우에 표시 됩니다. 기본 동작은 항상 명령을 표시 하는 것입니다.

 [KeyBindings 요소](../../extensibility/keybindings-element.md) -는 명령에 대 한 모든 키 바인딩을 지정 합니다. 즉, 하나 이상의 키 조합와 같은 명령을 실행 하려면 눌러야 하 **CTRL + S**합니다.

 [UsedCommands 요소](../../extensibility/usedcommands-element.md) -Informs는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 현재 VSPackage 활성화 된 경우 지정된 된 명령을 다른 코드에 의해 구현 되는 있지만 제공 하는 명령을 구현 하는 환경입니다.

 `Symbols Element` -기호 이름 및 패키지의 프로그램 명령을 모두에 대 한 GUID Id를 포함합니다.

## <a name="vsct-file-design-guidelines"></a>. Vsct 파일 디자인 지침
 .Vsct 파일을 성공적으로 디자인 하려면 다음이 지침을 따르십시오.

-   명령을 그룹에만 올 수 있습니다, 메뉴에 그룹을 배치할 수 있습니다 및 메뉴 그룹에만 올 수 있습니다. 메뉴만 그룹 IDE에 실제로 표시 되 고 명령을 가져오지 않습니다.

-   하위 메뉴는 메뉴에 직접 할당할 수 없습니다 되지만 메뉴에 다시 할당 되는 그룹에 할당 되어야 합니다.

-   하나의 부모/자식 관리 그룹 또는 해당 정의 지시문의 부모 필드를 사용 하 여 메뉴에 명령, 하위 메뉴 및 그룹을 할당할 수 있습니다.

-   지시문에 부모 필드를 통해서만 명령 테이블을 구성 하는 것은 중요 한 제한이 있습니다. 개체를 정의 하는 지시문은 단 하나의 부모만 인수를 받아들일 수 있습니다.

-   각각 개체의 새 인스턴스를 만드는 새 지시문을 사용 해야 명령, 그룹 또는 하위 메뉴를 다시 사용 `GUID:ID` 쌍입니다.

-   각 `GUID:ID` 쌍은 고유 해야 합니다. 에 의해 처리 됩니다, 예를 들어 배치 된 상황에 맞는 메뉴 또는 도구 모음, 메뉴 명령을 다시 사용 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다.

-   명령 및 하위 메뉴도 여러 그룹에 할당할 수 있으며 그룹을 사용 하 여 여러 메뉴에 지정할 수는 [Commands 요소](../../extensibility/commands-element.md)합니다.

## <a name="vsct-file-notes"></a>. Vsct 파일 정보
 실행 해야 하는 경우 변경 내용을.vsct 파일을 컴파일하려면와 네이티브 위성 DLL에에서 저장 한 후, **devenv.exe /setup /nosetupvstemplates**합니다. 이렇게 하면 읽어야 실험적 레지스트리 및 설명 하는 내부 데이터베이스에 지정 된 VSPackage 리소스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 다시 작성 해야 합니다.

 개발 하는 동안 여러 VSPackage 프로젝트를 만들고 IDE의 혼동 혼란을 일으킬 수 있는 실험적 레지스트리 하이브에 등록에 대 한 같습니다. 이 해결 하려면 실험 하이브에서 Vspackage 등록 된 모든 및 IDE에 변경한 수 내용을 제거 하려면 기본 설정으로 재설정할 수 있습니다. 실험 하이브를 다시 설정 하려면 Visual Studio SDK와 함께 제공 되 CreateExpInstance.exe 도구를 사용 합니다. 찾을 수 있습니다.

 **%PROGRAMFILES(x86)%\Visual Studio \<version> SDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe**

 명령줄을 사용 하 여 도구를 실행 **CreateExpInstance /Reset**합니다. 이 도구에서에서 제거 함을 실험 하이브에서 일반적으로 설치 된 모든 등록 된 Vspackage를 기억 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.

## <a name="see-also"></a>참고 항목
 [메뉴 및 명령 확장](../../extensibility/extending-menus-and-commands.md)
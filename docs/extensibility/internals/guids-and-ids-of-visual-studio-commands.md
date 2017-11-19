---
title: "Guid 및 Id를 Visual Studio 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ce546f36ed93f0f42bfd548c64f2a25669e162b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>Guid 및 Id를 Visual Studio 명령
Visual Studio 통합된 개발 환경 (IDE)에 포함 된 명령의 GUID 및 ID 값은 Visual Studio SDK의 일부로 설치 되는.vsct 파일에서 정의 됩니다. 자세한 내용은 참조 [IDE-Defined 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)합니다.  
  
 .Vsct 파일에 정의 되어 있는 IDE 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [확장 메뉴 및 명령을](../../extensibility/extending-menus-and-commands.md)합니다.  
  
## <a name="finding-a-command-definition"></a>명령 정의 찾기  
 Visual Studio는 1 천 개 이상의 명령을 정의 하므로 여기에 모두 나열 하는 것이 불가능 합니다. 대신 명령 정의를 찾으려면 다음이 단계를 수행 합니다.  
  
#### <a name="to-locate-a-command-definition"></a>명령 정의 찾을 수  
  
1.  Visual Studio에서 다음 파일을 열고는 *Visual Studio SDK 설치 경로*\VisualStudioIntegration\Common\Inc\ 폴더: SharedCmdDef.vsct, ShellCmdDef.vsct, VsDbgCmdUsed.vsct, Venusmenu.vsct 합니다.  
  
     대부분 Visual Studio 명령 SharedCmdDef.vsct 및 ShellCmdDef.vsct에 정의 됩니다. VsDbgCmdUsed.vsct 디버거, 관련 된 명령 정의 하 고 Venusmenu.vsct 웹 개발에 국한 되 명령입니다.  
  
2.  명령이 메뉴 항목 경우 note 메뉴 항목의 내용을 정확히 합니다. 명령을 도구 모음에 단추 경우 note에 놓으면 나타나는 도구 설명 텍스트입니다.  
  
3.  CTRL + f를 열려면는 **찾을** 대화 상자.  
  
4.  에 **찾을 내용** 상자에 2 단계에서 기록해둔 텍스트를 입력 합니다.  
  
5.  확인 **모든 열린 문서** 에 표시 되는 **찾는 위치** 상자입니다.  
  
6.  클릭는 **다음 찾기** 에서 텍스트를 선택할 때까지 단추는 `<Strings>` 섹션은 [Button 요소](../../extensibility/button-element.md)합니다.  
  
     `<Button>` 명령에 표시 되는 요소는 명령을 정의 합니다.  
  
 명령 정의 발견 하면에 넣을 수 명령의 복사본을 다른 메뉴 또는 도구 모음을 만들어서는 [CommandPlacement 요소](../../extensibility/commandplacement-element.md) 동일한를 있는 `guid` 및 `id` 명령으로는 값입니다. 자세한 내용은 참조 [단추의 다시 사용할 수 있는 그룹 만들기](../../extensibility/creating-reusable-groups-of-buttons.md)합니다.  
  
### <a name="special-cases"></a>특별 한 경우  
 다음과 같은 경우에 메뉴 텍스트 또는 도구 설명 텍스트 다 명령 정의에 포함 된 내용입니다.  
  
-   와 같은 밑줄이 그어진 문자를 포함 하는 메뉴 항목의 **인쇄** 명령을 **파일** 메뉴에서 P 밑줄이 표시 됩니다.  
  
     메뉴 항목 이름에 '&' 문자 뒤에 나오는 문자가 표시될지 밑줄이 합니다. 그러나.vsct 파일은 '&' 문자를 사용 하 여 특수 문자를 나타내기 위해 하며 표시 되는 앰퍼샌드를 입력 해야 하는 XML에 '&amp;'. 따라서.vsct 파일에에서는 **P**rint 명령으로 표시 '&amp;인쇄 '.  
  
-   명령의 동적 텍스트와 같은 **저장** *현재 파일 이름을*에 항목과 같은 새 메뉴 항목을 동적으로 생성 하 고는 **최근에 사용한 파일** 목록입니다.  
  
     동적 텍스트를 검색 하기 위해 신뢰할 수 있는 방법은 없습니다. 대신 참조 하 여 원하는 명령을 호스팅하는 그룹을 찾을 [Guid 및 Visual Studio 메뉴 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 또는 [Guid 및 Id의 Visual Studio 도구 모음](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md), 해당 그룹의 id를 검색 합니다. 명령 정의 그룹을이 없는 경우 해당 [부모 요소](../../extensibility/parent-element.md), 검색할 SharedCmdPlace.vsct 및 ShellCmdPlace.vsct (또는 디버거 명령에 대 한 VsDbgCmdPlace.vsct)는 `<CommandPlacement>` 의 부모를 설정 하는 요소는 명령입니다. 에 있는 SharedCmdPlace.vsct, ShellCmdPlace.vsct, andVsDbgCmdPlace.vsct는 *Visual Studio SDK 설치 경로*\VisualStudioIntegration\Common\Inc\ 폴더입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MenuCommand 및 OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)   
 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)
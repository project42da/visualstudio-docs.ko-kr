---
title: "격리 된 셸 사용 하 여 수정 된 합니다. Vsct 파일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode, .vsct file
ms.assetid: 6d147c2d-10e9-400e-b8ce-5566287b41ba
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9044821c2bfee0dba8ffa91f3d91afd565b8d957
ms.openlocfilehash: a20b546c6e8d6d70a17d3d0bae575a5b2898d781
ms.lasthandoff: 02/22/2017

---
# <a name="modifying-the-isolated-shell-by-using-the-vsct-file"></a>격리 된 셸 사용 하 여 수정 된 합니다. Vsct 파일
Visual Studio 격리 된 셸 프로젝트에 대 한 UI 프로젝트는 응용 프로그램에서 사용할 수 있는 어떤 응용 프로그램 그룹 및 개별 명령을 지정할 수 있는.vsct 파일을 포함 합니다. 다음은 수정 되지 않은.vsct 파일의 일부입니다.  
  
```  
<!-- <Define name="No_WindowListCommand"/> -->  
<!-- <Define name="No_MoreWindowsCommand"/> -->  
<!-- <Define name="No_PaneNextPaneCommand"/> -->  
<!-- <Define name="No_PanePrevPaneCommand"/> -->  
```  
  
 기본적으로 대부분의 명령 및 명령 그룹 포함 됩니다. 명령 또는 명령 그룹을 제외 하려면 단순히 주석 처리를 제거 명령이 나 그룹에 해당 합니다.  
  
 예를 들어 다음 창 및 이전 창 명령을 제거 하려면 주석 처리를 제거는 `No_PaneNextPaneCommand` 및 `No_PanePrevPaneCommand` 항목:  
  
```  
  
<Define name="No_PaneNextPaneCommand"/> <Define name="No_PanePrevPaneCommand"/>  
  
```  
  
 예제에 대 한 세부 이러한 사용자 지정, 참조 [연습: 기본 격리 된 셸 응용 프로그램을 만드는](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
## <a name="referenced-files"></a>참조 된 파일  
 응용 프로그램에 대 한 기본.vsct 파일 다음 파일을 참조합니다. 이러한 파일은 Visual Studio SDK 설치 디렉터리의 \VisualStudioIntegration\Common\Inc\ 하위 디렉터리에 있습니다.  
  
|파일|설명|  
|----------|-----------------|  
|wbids.h|웹 탐색 패키지에 대 한 UI id입니다.|  
|AppIDCmdUsed.vsct|기본 Visual Studio UI 요소에 대 한 명령 테이블입니다.|  
|EmulatorCmdUsed.vsct|Emacs 및 Brief 편집기 에뮬레이션 UI 요소에 대 한 명령 테이블입니다.|  
|Vsdebugguids.h|명령, 옵션 페이지 및 기타 기능에서 Visual Studio 디버거의 Guid를 정의합니다.|  
|VsDbgCmdUsed.vsct|디버거 명령 테이블입니다.|  
  
 AppIDCmdUsed.vsct 파일에는 응용 프로그램.vsct 파일에 정의 된 기호에 따라 Visual Studio UI 요소가 포함 됩니다.  
  
 자세한 내용은 참조 [XML 명령 테이블 디자인 (합니다. Vsct) 파일](../extensibility/internals/designing-xml-command-table-dot-vsct-files.md) 및 [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio Shell 격리](../extensibility/visual-studio-isolated-shell.md)

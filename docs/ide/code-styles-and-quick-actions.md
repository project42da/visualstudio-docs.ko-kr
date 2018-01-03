---
title: "Visual Studio 코드 스타일 기본 설정 | Microsoft Docs"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload: multiple
ms.openlocfilehash: 80b7260296f1f57448ae94147a59dbb29160be40
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="code-style-preferences"></a>코드 스타일 기본 설정

**도구** 메뉴에서 **옵션** 대화 상자를 열어 C# 및 Visual Basic 프로젝트에 대한 코드 스타일 기본 설정을 설정할 수 있습니다. **텍스트 편집기**, **C#** 또는 **기본**, **코드 스타일**, **일반**을 선택합니다. 이 창에서 설정한 옵션은 로컬 컴퓨터에 적용됩니다. 목록의 각 항목에는 아래와 같이 선택한 기본 설정의 미리 보기가 표시됩니다.

![코드 스타일 옵션](media/code-style-quick-actions-dialog.png)

각 항목에 대해 각 줄에 있는 드롭다운을 사용하여 **기본 설정** 및 **심각도**를 설정할 수 있습니다. 심각도는 **없음**, **제안**, **경고** 또는 **오류**로 설정할 수 있으며 Visual Studio는 적절하게 동작합니다. 이러한 코드 스타일에서 [빠른 작업](quick-actions.md)을 사용하여 기본 스타일로 코드를 자동으로 다시 작성하려는 경우 설정을 **없음**이 아닌 다른 설정으로 지정하여, 기본이 아닌 스타일을 사용될 때 전구 아이콘 ![작은 전구 아이콘](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall")이 나타나도록 합니다. 그러면 이러한 기본 설정은 커서가 적절한 코드 줄에 있을 때 전구 아이콘을 클릭하거나 **Ctrl+.**를 눌러 적용할 수 있습니다.

또한 .NET에 대한 코드 스타일 설정은 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 파일을 사용하여 관리할 수 있습니다. 이 경우에 EditorConfig 파일의 설정은 **옵션** 대화 상자에서 선택한 옵션보다 우선합니다. EditorConfig 파일을 사용하여 전체 리포지토리 또는 프로젝트에 코딩 스타일을 적용하고 구성할 수 있습니다.

## <a name="see-also"></a>참고 항목

[빠른 작업](quick-actions.md)  
[EditorConfig에 대한 .NET 코딩 규칙 설정](../ide/editorconfig-code-style-settings-reference.md)
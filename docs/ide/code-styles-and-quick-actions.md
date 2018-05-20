---
title: Visual Studio 코드 스타일 기본 설정
ms.date: 03/10/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 6dd046fa8a01cde7abdc33484da3ff8227eda966
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="code-style-preferences"></a>코드 스타일 기본 설정

**도구** 메뉴에서 **옵션** 대화 상자를 열어 C# 및 Visual Basic 프로젝트에 대한 코드 스타일 기본 설정을 설정할 수 있습니다. **텍스트 편집기** > **C#** 또는 **기본** > **코드 스타일** > **일반**을 선택합니다. 이 창에서 설정한 옵션은 로컬 컴퓨터에 적용됩니다.

목록의 각 항목에는 선택한 기본 설정의 미리 보기가 표시됩니다.

![코드 스타일 옵션](media/code-style-quick-actions-dialog.png)

## <a name="preference-and-severity"></a>기본 설정 및 심각도

각 항목에 대해 각 줄에 있는 드롭다운을 사용하여 **기본 설정** 및 **심각도** 값을 설정할 수 있습니다. 심각도는 **없음**, **제안**, **경고** 또는 **오류**로 설정할 수 있습니다. 코드 스타일에 대해 [빠른 작업](../ide/quick-actions.md)을 사용하려면 **심각도** 설정이 **없음** 이외의 값으로 설정되어 있는지 확인합니다. 선호하지 않는 스타일이 사용될 경우 빠른 작업 전구 아이콘![작은 전구 아이콘](media/vs2015_lightbulbsmall.png)이 표시되고, 빠른 작업 목록에서 옵션을 선택하면 코드를 원하는 스타일로 자동으로 다시 작성할 수 있습니다.

## <a name="editorconfig-files"></a>EditorConfig 파일

또한 .NET에 대한 코드 스타일 설정은 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 파일을 사용하여 관리할 수 있습니다. EditorConfig 파일의 설정은 **옵션** 대화 상자에서 선택한 옵션보다 우선합니다. EditorConfig 파일을 사용하여 전체 리포지토리 또는 프로젝트에 코딩 스타일을 적용하고 구성할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [빠른 작업](../ide/quick-actions.md)
- [EditorConfig에 대한 .NET 코딩 규칙 설정](../ide/editorconfig-code-style-settings-reference.md)
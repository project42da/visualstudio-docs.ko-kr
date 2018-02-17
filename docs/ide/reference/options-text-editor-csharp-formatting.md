---
title: "옵션, 텍스트 편집기, C#, 서식 | Microsoft Docs"
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.NewLines
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Indentation
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Wrapping
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.General
helpviewer_keywords:
- formatting options [C#]
- Text editor Options dialog box, formatting
ms.assetid: 5a7bb668-1d0c-4ffe-9508-24592813162e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 639082683ad0b65b294307df0740aa4d9c6069d0
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2018
---
# <a name="options-text-editor-c-formatting"></a>옵션, 텍스트 편집기, C#, 서식

**서식** 옵션 페이지를 사용하여 코드 편집기의 서식 코드에 대한 옵션을 설정합니다. 이 옵션 페이지에 액세스하려면 **도구** > **옵션**을 선택한 다음, **텍스트 편집기** > **C#** > **코드 스타일** > **서식**을 선택합니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

## <a name="general-settings"></a>일반 설정

일반 설정은 코드 편집기가 서식 옵션을 코드에 적용하는 방법에 영향을 미칩니다.

## <a name="uielement-list"></a>UI 요소 목록

|레이블|설명|
|-----------|-----------------|
|**입력할 때 서식 자동 지정**|이 옵션을 선택 취소하면 **입력 시 문 서식 지정;** 및 **입력 시 블록 서식 지정}** 옵션이 비활성화됩니다.|
|**입력 시 문 서식 자동 지정;**|이 옵션을 선택하면 편집기에 대해 선택된 서식 옵션에 따라 완성 시 문에 서식이 지정됩니다.|
|**입력 시 블록 서식 자동 지정}**|이 옵션을 선택하면 코드 블록을 완료하면 바로 편집기에 대해 선택된 서식 옵션에 따라 코드 블록에 서식이 지정됩니다.|
|**반환할 때 서식 자동 지정**|이 옵션을 선택하면 **Enter** 키를 누를 때 텍스트가 편집기에 대해 선택된 서식 옵션에 맞게 서식 지정됩니다.|
|**붙여넣을 때 서식 자동 지정**|이 옵션을 선택하면 편집기에 대해 선택된 서식 옵션에 맞게 편집기에 붙여넣는 텍스트에 서식이 지정됩니다.|

## <a name="preview-window"></a>미리 보기 창

**들여쓰기**, **줄 추가**, **간격** 및 **줄 바꿈** 옵션 창에는 각각 미리 보기 창이 표시됩니다. 미리 보기 창에는 각 옵션의 효과가 표시됩니다. 미리 보기 창을 사용하려면 서식 옵션을 선택합니다. 미리 보기 창에는 선택된 옵션의 예제가 표시됩니다. 라디오 단추 또는 확인란을 선택하여 설정을 변경하면 미리 보기 창이 업데이트되어 새 설정의 효과가 표시됩니다.

## <a name="remarks"></a>설명

각 언어에 대한 **탭** 페이지의 들여쓰기 옵션은 줄 끝에서 **Enter** 키를 누를 때 코드 편집기에서 커서가 배치되는 위치만 결정합니다. **서식** 아래 들여쓰기 옵션은 코드 서식이 자동으로 지정되는 경우 적용됩니다(예: **붙여넣을 때 서식 자동 지정**이 선택된 동안 코드를 파일에 붙여넣을 경우, 그리고 서식 지정되는 블록이 수동으로 입력되는 경우).

## <a name="see-also"></a>참고 항목

[옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)

---
title: "옵션, 텍스트 편집기, C#, 서식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Spacing"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.NewLines"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting.General"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Indentation"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting.NewLines"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting.Indentation"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting.Wrapping"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Wrapping"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.General"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting.Spacing"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Formatting"
helpviewer_keywords: 
  - "서식 지정[C#]"
  - "서식 지정[J#]"
  - "텍스트 편집기 옵션 대화 상자, 서식 지정"
ms.assetid: 5a7bb668-1d0c-4ffe-9508-24592813162e
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 옵션, 텍스트 편집기, C#, 서식
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**서식** 속성 페이지 대화 상자를 사용하여 코드 편집기의 코드 서식에 대한 옵션을 설정할 수 있습니다.  이 대화 상자에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭하고 **텍스트 편집기**, **C\#**을 차례로 확장한 다음 **서식**을 클릭합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 일반 설정  
 일반 설정은 코드 편집기가 코드에 서식 옵션을 적용하는 방법에 영향을 줍니다.  
  
## UI 요소 목록  
  
|레이블|설명|  
|---------|--------|  
|**; 입력 시 완성 문에 서식 자동 지정**|이 옵션을 선택하면 코드 편집기에서 선택한 서식 옵션에 따라 자동 완성 문의 서식이 지정됩니다.  코드 편집기에서 문이 변경되지 않도록 하려면 이 확인란의 선택을 취소합니다.|  
|**} 입력 시 완성 블록에 서식 자동 지정**|이 옵션을 선택하면 코드 블록을 완성하는 즉시 코드 편집기에서 선택된 서식 옵션에 따라 코드 블록 서식이 지정됩니다.  코드 편집기에서 블록이 변경되지 않도록 하려면 이 확인란의 선택을 취소합니다.|  
|**붙여넣을 때 들여쓰기 조정**|이 옵션을 선택하면 코드 편집기로 붙여넣는 텍스트의 서식은 코드 편집기에서 선택된 서식 옵션에 맞게 지정됩니다.  붙여넣는 텍스트가 변경되지 않도록 하려면 이 확인란의 선택을 취소합니다.|  
  
## 미리 보기 창  
 **들여쓰기**, **줄 추가**, **간격** 및 **줄 바꿈** 옵션 창은 각각 미리보기 창을 표시합니다.  미리보기 창에는 각 옵션의 효과가 표시됩니다.  미리보기 창을 사용하려면 서식 옵션을 선택합니다.  미리보기 창에는 선택된 옵션의 보기가 표시됩니다.  확인란을 선택하거나 선택을 취소하는 등 설정을 변경하면 새 설정의 효과를 보여 주도록 미리 보기 창이 업데이트됩니다.  
  
## 설명  
 각 언어에 대한 **탭** 페이지의 들여쓰기 옵션은 사용자가 줄 끝에서 Enter 키를 눌렀을 때 코드 편집기에서 커서가 놓이는 위치를 결정합니다.  **서식**에 있는 들여쓰기 옵션은 코드 서식이 자동으로 지정될 때 적용됩니다. 예를 들면 **붙여넣을 때 들여쓰기 조정**이 선택된 상태에서 파일에 코드를 붙여넣을 때 또는 서식 지정할 블록을 수동으로 입력할 때 적용됩니다.  
  
## 참고 항목  
 [옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)
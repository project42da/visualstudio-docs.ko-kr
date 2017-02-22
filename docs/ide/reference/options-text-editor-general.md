---
title: "일반, 텍스트 편집기, 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL"
  - "VS.ToolsOptionsPages.Text_Editor.All_Languages.General"
  - "VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General"
  - "VS.ToolsOptionsPages.Text_Editor.SQL.General"
  - "vs.toolsoptionspages.text_editor"
  - "VS.ToolsOptionsPages.Text_Editor.XML.General"
  - "VS.ToolsOptionsPages.Text_Editor.T-SQL80.General"
  - "VS.ToolsOptionsPages.Text_Editor.CSS"
  - "VS.ToolsOptionsPages.Text_Editor.Plain_Text.General"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.General"
  - "VS.ToolsOptionsPages.Text_Editor.SQL_Script.General"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.General"
  - "VS.ToolsOptionsPages.Text_Editor.All_Languages"
  - "VS.ToolsOptionsPages.Text_Editor.T-SQL7.General"
  - "VS.ToolsOptionsPages.Text_Editor.Basic.General"
  - "VS.ToolsOptionsPages.Text_Editor.T-SQL.General"
  - "vs.toolsoptionspages.text_editor.visual_jsharp"
  - "VS.ToolsOptionsPages.Text_Editor.F#.Tabs"
  - "VS.ToolsOptionsPages.Text_Editor.F#"
  - "VS.ToolsOptionsPages.Text_Editor.PL/SQL.General"
  - "VS.ToolsOptionsPages.Text_Editor.C/C++.General"
  - "VS.ToolsOptionsPages.Text_Editor.Plain_Text"
  - "VS.ToolsOptionsPages.Text_Editor.HTML"
  - "VS.ToolsOptionsPages.Text_Editor.XAML.General"
  - "VS.ToolsOptionsPages.Text_Editor"
  - "VS.ToolsOptionsPages.Text_Editor.F#.General"
  - "VS.ToolsOptionsPages.Text_Editor.XOML.General"
  - "VS.ToolsOptionsPages.Text_Editor.SQL"
  - "vs.toolsoptionspages.text_editor.c/c++"
  - "VS.ToolsOptionsPages.Text_Editor.SQL_Script"
  - "VS.ToolsOptionsPages.Text_Editor.T-SQL90.General"
  - "VS.ToolsOptionsPages.Text_Editor.General"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp"
helpviewer_keywords: 
  - "텍스트 편집기 옵션 대화 상자"
  - "코드 편집기"
  - "텍스트 편집기[Visual Studio]"
  - "편집기, 전역 설정"
ms.assetid: 4ac21e48-3243-4141-9058-7eaf12b3cde7
caps.latest.revision: 29
caps.handback.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 일반, 텍스트 편집기, 옵션
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 대화 상자에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코드 및 텍스트 편집기에 대한 전역 설정을 변경할 수 있습니다.  이 대화 상자를 표시하려면 **도구** 메뉴에서 **옵션**을 클릭하고 **텍스트 편집기** 폴더를 확장한 다음 **일반**을 클릭합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 설정  
 텍스트 끌어서 놓기  
 이 옵션을 선택하면 텍스트를 선택한 다음 마우스로 끌어서 현재 문서 내의 다른 위치 또는 열려 있는 다른 문서로 이동할 수 있습니다.  
  
 구분 기호 자동 강조  
 이 옵션을 선택하면 짝을 이루는 괄호뿐 아니라 매개 변수나 항목\-값 쌍을 구분하는 구분 기호가 강조됩니다.  
  
 변경 내용 추적  
 코드 편집기를 선택 하면 노란색 세로줄이 파일이 가장 최근에 저장 된 이후 변경 된 코드를 표시 하려면 선택 영역 여백에 나타납니다.  변경 내용을 저장 하면 세로줄이 녹색 됩니다.  
  
 서명 없는 UTF\-8 인코딩 자동 검색  
 기본적으로 편집기는 바이트 순서 표시나 charset 태그를 검색하여 인코딩을 검색합니다.  현재 문서에 두 가지 모두 없으면 코드 편집기는 바이트 시퀀스를 검색하여 UTF\-8 인코딩을 자동으로 검색합니다.  인코딩 자동 검색을 사용하지 않으려면 이 옵션 선택을 취소합니다.  
  
## 표시  
 선택 영역 여백  
 이 옵션을 선택하면 편집기의 텍스트 영역 왼쪽 가장자리를 따라 세로 여백이 표시됩니다.  이 여백을 클릭하면 텍스트 한 줄 전체를 선택할 수 있고, 클릭하고 끌면 연속하는 여러 줄의 텍스트를 선택할 수 있습니다.  
  
|선택 영역 여백 설정|선택 영역 여백 해제|  
|-----------------|-----------------|  
|![HTMLpageSelectionMarginOn 스크린 샷](../../ide/reference/media/vxselmaron.png "vxSelmaron")|![HTMLpageSelectionMarginOff 스크린 샷](../../ide/reference/media/vxselmaroff.gif "vxSelmaroff")|  
  
 표시기 여백  
 이 옵션을 선택하면 편집기의 텍스트 영역 왼쪽 가장자리 바깥쪽에 여백이 표시됩니다.  이 여백을 클릭하면 텍스트와 관련된 아이콘과 도구 설명이 나타납니다.  예를 들어, 표시기 여백에는 중단점이나 작업 목록 바로 가기가 나타납니다.  표시기 여백 정보는 인쇄되지 않습니다.  
  
 세로 스크롤 막대  
 이 옵션을 선택하면 위 아래로 스크롤하여 편집기의 가시 영역 외부에 있는 요소를 볼 수 있는 세로 스크롤 막대가 표시됩니다.  세로 스크롤 막대를 사용할 수 없으면 페이지 위로, 페이지 아래로 및 커서 키를 사용하여 스크롤할 수 있습니다.  
  
 가로 스크롤 막대  
 이 옵션을 선택하면 옆으로 스크롤하여 편집기의 가시 영역 외부에 있는 요소를 볼 수 있는 가로 스크롤 막대가 표시됩니다.  가로 스크롤 막대를 사용할 수 없으면 커서 키를 사용하여 스크롤할 수 있습니다.  
  
 현재 줄 강조 표시  
 옵션을 선택 하면 커서가 위치한 코드 줄 주위에 회색 상자가 표시 됩니다.  
  
## 참고 항목  
 [옵션, 텍스트 편집기, 모든 언어](../../ide/reference/options-text-editor-all-languages.md)   
 [옵션, 텍스트 편집기, 모든 언어, 탭](../../ide/reference/options-text-editor-all-languages-tabs.md)   
 [옵션, 텍스트 편집기, 파일 확장명](../../ide/reference/options-text-editor-file-extension.md)   
 [바로 가기 키 식별 및 사용자 지정](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)   
 [편집기 사용자 지정](../../ide/customizing-the-editor.md)   
 [IntelliSense 사용](../../ide/using-intellisense.md)
---
title: "옵션 대화 상자, Microsoft Office 키보드 설정, Microsoft Office Excel 키보드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VST.ExcelOptions.KeyboardMappingScheme"
  - "VS.ToolsOptionsPages.Microsoft_Office_Keyboard_Settings.Microsoft_Office_Excel_Keyboard"
  - "VS.ToolsOptionsPages.Microsoft_Office_Tools.Microsoft_Office_Excel.Keyboard"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "바로 가기 키, Visual Studio에서 Office 개발"
ms.assetid: 2a8b9e70-66fa-4461-8039-b6d8a2fbb963
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# 옵션 대화 상자, Microsoft Office 키보드 설정, Microsoft Office Excel 키보드
  Microsoft Office Excel 및 Visual Studio 모두 바로 가기 키를 처리합니다.  동일한 바로 가기 키 조합이 Excel과 Visual Studio에서 서로 다른 명령을 나타낼 수 있습니다.  Excel이 Visual Studio의 문서 수준의 프로젝트에 열려 있는 경우 한 번에 하나의 응용 프로그램만 바로 가기 키 명령을 받습니다.  기본적으로는 Visual Studio에서 모든 바로 가기 키 명령을 받지만 **동적 키보드 구성표**를 선택하여 문서에 포커스가 있을 때 Excel에서 바로 가기 키 명령을 받도록 할 수 있습니다.  
  
 현재 바로 가기 키를 처리 중인 응용 프로그램에서 명령에 할당되지 않은 바로 가기 키를 사용하는 경우 바로 가기 키는 다른 응용 프로그램에 전달됩니다.  
  
 선택한 옵션은 다시 변경할 때까지 Excel 프로젝트에 적용됩니다.  이러한 선택 내용은 Microsoft Office Word 프로젝트에는 영향을 주지 않습니다. Word에 대한 옵션을 변경하려면 Microsoft Office Word 키보드 옵션을 사용해야 합니다.  
  
## UI 요소 목록  
 **Visual Studio 키보드 구성표**  
 모든 바로 가기 키 명령이 Visual Studio로 전달되며, Excel에 포커스가 있는 경우에도 마찬가지입니다.  예를 들어 Excel에 포커스가 있는 동안 F5 기능 키를 누르면 Visual Studio에서 솔루션 디버깅이 시작됩니다.  
  
 **동적 키보드 구성표**  
 Visual Studio에 포커스가 있을 때에만 Visual Studio가 바로 가기 키 명령을 받습니다.  Excel에 포커스가 있으면 Excel이 모든 바로 가기 키 명령을 받습니다.  예를 들어 Excel에 포커스가 있는 동안 F5 기능 키를 누르면 Excel에서 **이동** 대화 상자가 열립니다.  Visual Studio에 포커스가 있는 동안 F5 키를 누르면 Visual Studio에서 솔루션 디버깅이 시작됩니다.  
  
## 참고 항목  
 [옵션 대화 상자, Microsoft Office 키보드 설정, Microsoft Office Word 키보드](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)  
  
  
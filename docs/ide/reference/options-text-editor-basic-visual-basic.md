---
title: "옵션, 텍스트 편집기, 기본(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Visual_Basic.Editor"
  - "VS.ToolsOptionsPages.Text_Editor.Basic.Editor"
  - "VS.ToolsOptionsPages.Visual_Basic_Editor.Editor"
  - "VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage"
  - "VS.ToolsOptionsPages.Text_Editor.Basic"
  - "VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific"
helpviewer_keywords: 
  - "기본 텍스트 편집기 옵션 대화 상자"
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 옵션, 텍스트 편집기, 기본(Visual Basic)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**옵션**\(**도구** 메뉴\) 대화 상자에서 **텍스트 편집기** 폴더 아래에 있는 **Basic** 폴더의 **VB 관련** 속성 페이지에는 다음 속성이 포함되어 있습니다.  
  
 **맺음 구문 자동 삽입**  
 예를 들어, 프로시저 선언의 첫째 줄인 `Sub Main—`을 입력하고 Enter 키를 누르면 텍스트 편집기에서는 짝을 이루는 `End Sub` 줄을 추가합니다.  마찬가지로 [For](/dotnet/visual-basic/language-reference/statements/for-next-statement) 루프를 입력하면 짝을 이루는 `Next` 문이 추가됩니다.  이 옵션을 선택하면 코드 편집기에서 자동으로 종료 구문을 추가합니다.  
  
 **코드 서식 다시 적용**  
 텍스트 편집기는 코드 서식을 적절하게 다시 적용합니다.  이 옵션을 선택하면 코드 편집기에서 다음을 수행합니다.  
  
-   올바른 탭 위치에 맞추어 코드 정렬  
  
-   키워드, 변수 및 개체의 대\/소문자를 올바르게 수정  
  
-   `If...Then` 문에 빠진 `Then` 추가  
  
-   함수 호출에 괄호 추가  
  
-   문자열에 빠진 닫는 따옴표 추가  
  
-   지수 표기 서식 다시 적용  
  
-   날짜 서식 다시 적용  
  
 **개요 모드 사용**  
 코드 편집기에서 파일을 열면 문서를 개요 모드로 볼 수 있습니다.  자세한 내용은 [개요](../../ide/outlining.md)를 참조하십시오.  이 옵션을 선택하고 파일을 열면 개요 기능이 활성화됩니다.  
  
 **인터페이스 및 MustOverride 멤버 자동 삽입**  
 클래스에 `Implements` 문이나 `Inherits` 문을 커밋할 때 텍스트 편집기에서 구현하거나 재정의해야 하는 멤버의 프로토타입을 삽입합니다.  
  
 **프로시저 줄 구분선 표시**  
 텍스트 편집기에서 프로시저의 시각적인 범위를 표시합니다.  프로젝트의 .vb 소스 파일에서 다음 표에 나열된 위치에 줄이 표시됩니다.  
  
|.vb 소스 파일의 위치|줄 위치 예제|  
|-------------------|-------------|  
|블록 선언 구문의 끝 뒤|-   class, structure, module, interface 또는 enum의 끝<br />-   property, function 또는 sub 뒤<br />-   property의 get 및 set 절 사이에는 없음|  
|한 줄로 된 구문 뒤|-   import 문 뒤, 클래스 파일의 형식 정의 앞<br />-   클래스에 선언된 변수 뒤, 모든 프로시저 앞|  
|한 줄로 된 선언 뒤\(블록 수준 이외의 선언\)|-   import 문, inherits 문, 변수 선언, 이벤트 선언, 대리자 선언 및 DLL declare 문 다음|  
  
 **오류 수정 제안 사용**  
 텍스트 편집기에서 일반적인 오류의 해결 방법을 제안하고 코드에 적용되는 적절한 수정을 선택할 수 있게 합니다.  
  
 **참조 및 키워드의 강조 표시 사용**  
 텍스트 편집기는 `If..Then`, `While...End While` 또는 `Try...Catch...Finally` 같은 절에서 기호의 모든 인스턴스 또는 모든 키워드를 강조 표시할 수 있습니다.  Ctrl \+ Shift \+ 아래쪽 화살표 또는 Ctrl \+ Shift \+ 위쪽 화살표 키를 눌러 강조 표시된 참조 또는 키워드 간에 이동할 수 있습니다.  
  
## 참고 항목  
 [옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)   
 [옵션, 텍스트 편집기, 모든 언어, 탭](../../ide/reference/options-text-editor-all-languages-tabs.md)
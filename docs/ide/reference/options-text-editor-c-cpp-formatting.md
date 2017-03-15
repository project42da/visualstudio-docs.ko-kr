---
title: "옵션, 텍스트 편집기, C/C++, 서식 | Microsoft Docs"
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
  - "VS.ToolsOptionsPages.Text_Editor.C/C++.Formatting.General"
  - "VS.ToolsOptionsPages.Text_Editor.C%2fC%2b%2b.Formatting.General"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "텍스트 편집기 옵션 대화 상자, 서식 지정"
ms.assetid: cb6f1cbb-5305-48da-a8e8-33fd70775d46
caps.latest.revision: 16
caps.handback.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 옵션, 텍스트 편집기, C/C++, 서식
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

C 또는 C\+\+로 프로그래밍할 때 코드 편집기의 기본 동작을 변경할 수 있습니다.  
  
 이 페이지에 액세스하려면 왼쪽 창의 **옵션** 대화 상자에서 **텍스트 편집기**를 확장하고 **C\/C\+\+**를 확장한 다음 **서식**을 클릭합니다.  
  
> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## C\/C\+\+ 옵션  
 **요약 정보 자동 표시 도구 설명 사용**  
 요약 정보 IntelliSense 기능을 사용하거나 사용하지 않도록 설정합니다.  
  
## 비활성 코드  
 **비활성 코드 블록 표시**  
 `#ifdef` 선언으로 인해 비활성화된 코드는 이를 식별할 수 있도록 다른 색으로 표시됩니다.  
  
 **비활성 코드 불투명 사용 안 함**  
 비활성 코드는 투명도 대신 색상을 사용하여 식별할 수 있습니다.  
  
 **비활성 코드 불투명도\(%%\)**  
 비활성 코드 블록에 대한 불투명도 수준은 사용자 지정할 수 있습니다.  
  
## 들여쓰기  
 **중괄호 들여쓰기**  
 함수 또는 `for` 루프 같은 코드 블록을 시작한 후에 Enter 키를 누르면 괄호가 정렬되는 방법을 구성할 수 있습니다.  중괄호는 코드 블록 또는 들여쓴 첫 번째 문자에 정렬할 수 있습니다.  
  
 **탭에서 자동 들여쓰기**  
 Tab 키를 누르면 현재 코드 줄에 발생하는 동작을 구성할 수 있습니다.  줄이 들여쓰기되거나 탭이 삽입됩니다.  
  
## 기타  
 **작업 목록 창에 주석 열거**  
 편집기에서는 주석에 있는 미리 설정된 단어에 대한 오픈 소스 파일을 검색할 수 있습니다.  발견한 키워드에 대해 **작업 목록** 창에 항목을 만듭니다.  
  
 **일치 토큰 강조 표시**  
 커서가 중괄호 옆에 있을 때 편집기에서 포함된 코드를 보다 쉽게 볼 수 있도록 짝이 되는 중괄호를 강조 표시할 수 있습니다.  
  
## 개요  
 **개요 모드로 파일 열기**  
 파일을 텍스트 편집기로 가져오면 개요 기능을 사용할 수 있습니다.  자세한 내용은 [개요](../../ide/outlining.md)을 참조하십시오.  이 옵션을 선택하고 파일을 열면 개요 기능이 활성화됩니다.  
  
 **\#pragma 영역 블록을 자동으로 개요 표시**  
 이 옵션을 선택하면 [pragma 지시문](/visual-cpp/preprocessor/pragma-directives-and-the-pragma-keyword)의 자동 개요 표시를 사용할 수 있습니다.  개요 모드에서 이 pragma 영역 블록을 확장하거나 축소할 수 있습니다.  
  
 **문 블록을 자동으로 개요 표시**  
 이 옵션이 선택되면 다음 구문에 대해 자동 개요가 활성화됩니다.  
  
-   [if\-else](/dotnet/csharp/language-reference/keywords/if-else)  
  
-   [switch 문 \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)  
  
-   [while 문 \(C\+\+\)](/visual-cpp/cpp/while-statement-cpp)  
  
## 참고 항목  
 [옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)   
 [IntelliSense 사용](../../ide/using-intellisense.md)
---
title: "옵션, 텍스트 편집기, C#, 고급 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Advanced"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Outlining"
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced"
helpviewer_keywords: 
  - "XML 주석"
  - "XML 문서, 생성"
  - "개요 옵션[C#]"
  - "개요 옵션[J#]"
  - "XML 문서, 만들기"
ms.assetid: 947f9d9a-b0f3-408d-9866-d82895bcee31
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 옵션, 텍스트 편집기, C#, 고급
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 대화 상자를 사용하여 Visual C\#에 대한 편집기 서식, 코드 리팩터링 및 XML 문서 주석에 대한 설정을 수정할 수 있습니다.  이 대화 상자에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭하고 **텍스트 편집기** 폴더, **C\#**을 차례로 확장한 다음 **고급**을 클릭합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 개요  
 개요 모드로 파일 열기  
 이 옵션을 선택하면 자동으로 코드 파일이 요약되어 축소 가능한 코드 블록이 만들어집니다.  파일이 처음 열릴 때 \#regions 블록과 비활성 코드 블록이 축소됩니다.  
  
## 편집기 도움말  
 편집기에서 오류에 밑줄 표시  
 코드에서 빌드 오류를 식별합니다.  이 옵션을 선택하면 특정한 의미가 있는 색으로 물결선이 나타납니다.  
  
-   구문 분석 오류는 빨간색입니다.  
  
-   빌드 오류는 파란색입니다.  
  
-   빌드 경고는 녹색입니다.  
  
-   잘못된 [편집하며 계속하기](../../debugger/edit-and-continue.md) 편집 내용은 자주색입니다.  
  
 포인터를 밑줄이 있는 코드 세그먼트로 이동하면 오류에 대한 정보를 표시하는 도구 설명을 볼 수 있습니다.  
  
 라이브 의미 오류 표시  
 특정 컴파일 오류의 경우 알 수 없는 형식을 선언 및 사용하거나 알 수 없는 속성을 참조하는 등 명시적 컴파일 없이 식별합니다.  
  
 커서 아래 기호에 대한 참조를 강조 표시  
 커서가 기호 안에 위치해 있거나 기호를 클릭하면 코드 파일에 속한 해당 기호의 모든 인스턴스가 강조 표시됩니다.  
  
## 리팩터링  
 리팩터링의 결과 확인  
 빌드 오류가 있는 코드를 리팩터링하려고 할 때나 리팩터링으로 인해 코드 참조가 원래 바인딩과 다른 것에 바인딩될 때 **확인 결과** 대화 상자를 표시합니다.  
  
 컴파일러에서 생성한 참조가 있는 멤버에 대해 경고  
 컴파일러에서 생성한 참조와 동일한 이름이 있는 멤버를 리팩터링하려고 하면 경고 대화 상자가 표시됩니다.  
  
## XML 문서 주석  
 \/\/\/에 대해 XML 문서 주석 생성  
 이 옵션을 선택하면 사용자가 주석 시작을 나타내는 \/\/\/를 입력한 후 XML 문서 주석에 대해 자동으로 \<summary\> 시작 및 끝 태그가 삽입됩니다.  XML 문서에 대한 자세한 내용은 [XML 문서 주석](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)을 참조하십시오.  
  
## 인터페이스 구현  
 \#region으로 생성된 코드 감싸기  
 인터페이스 구현 또는 명시적으로 인터페이스 구현을 사용하는 경우 메서드 주변에 \#region \<*interface name*\> 멤버를 삽입합니다.  
  
## Using 구성  
 using 정렬 시 'System' 지시문 먼저 배치  
 이 옵션을 선택하면 다른 using 지시문 전에 `System` using 지시문이 나타납니다.  자세한 내용은 [Using 정렬](../../misc/sort-usings.md)을 참조하십시오.  
  
## 참고 항목  
 [XML 문서 주석](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [언어별 편집기 옵션 설정](../../ide/reference/setting-language-specific-editor-options.md)   
 [Visual C\# IntelliSense](../../ide/visual-csharp-intellisense.md)
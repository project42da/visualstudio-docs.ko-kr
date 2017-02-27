---
title: "옵션, 텍스트 편집기, C#, IntelliSense | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense"
  - "VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Intellisense"
helpviewer_keywords: 
  - "IntelliSense[J#], 옵션"
  - "밑줄, 물결 무늬"
  - "IntelliSense[C#], 옵션"
  - "IntelliSense[C#], 물결 무늬 밑줄"
  - "물결선"
  - "텍스트 편집기 옵션 대화 상자, IntelliSense"
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
caps.latest.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 옵션, 텍스트 편집기, C#, IntelliSense
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**IntelliSense** 속성 페이지를 사용하여 Visual C\#에 대한 IntelliSense의 동작에 영향을 주는 설정을 수정할 수 있습니다.  **IntelliSense** 속성 페이지에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭하고 **텍스트 편집기**에서 **C\#**을 클릭한 다음 **IntelliSense**를 클릭합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 **IntelliSense** 속성 페이지에는 다음 속성이 포함되어 있습니다.  
  
## 완성 목록  
 **문자를 입력하면 완성 목록 표시**  
 이 옵션을 선택하면 사용자가 입력을 시작할 때 IntelliSense는 자동으로 완성 목록을 표시합니다.  이 옵션을 선택하지 않더라도 **IntelliSense** 메뉴를 사용하거나 Ctrl\+스페이스를 눌러 IntelliSense 완성 기능을 이용할 수 있습니다.  
  
 **완성 목록에 키워드 배치**  
 이 옵션을 선택하면 IntelliSense는 C\# 키워드\(예: [클래스](/dotnet/csharp/language-reference/keywords/class)\)를 완성 목록에 추가합니다.  
  
 **완성 목록에 코드 조각 배치**  
 이 옵션을 선택하면 IntelliSense는 C\# 코드 조각의 별칭을 완성 목록에 추가합니다.  코드 조각 별칭이 키워드와 같은 경우\(예: [클래스](/dotnet/csharp/language-reference/keywords/class)\) 해당 키워드는 바로 가기로 바뀝니다.  자세한 내용은 [Visual C\# 코드 조각](../../ide/visual-csharp-code-snippets.md)를 참조하십시오.  
  
## 완성 목록의 선택 항목  
 **다음 문자를 입력하면 커밋됨:**  
 입력되면 완성 목록의 선택된 항목에 대한 IntelliSense 자동 완성을 실행하는 모든 문자를 지정합니다.  
  
 **스페이스바를 누르면 커밋됨**  
 스페이스바를 누르면 완성 목록의 선택된 항목에 대한 IntelliSense 자동 완성을 실행하는 동작을 포함하도록 지정합니다.  
  
 **단어를 모두 입력한 후 \<Enter\> 키를 누르면 새 줄 추가**  
 완성 목록에 있는 항목의 모든 문자를 입력한 다음 Enter 키를 누르면 자동으로 새 줄이 생성되어 커서가 새 줄로 이동하도록 지정합니다.  
  
 예를 들어 `else`를 입력한 다음 Enter 키를 누르면 편집기에서 다음과 같은 결과를 볼 수 있습니다.  
  
 `else`  
  
 `|` \(커서 위치\)  
  
 하지만 `el`만 입력한 다음 Enter 키를 누르면 편집기에서 다음과 같은 결과를 볼 수 있습니다.  
  
 `else|`\(커서 위치\)  
  
## IntelliSense 멤버 선택  
 **가장 최근에 사용한 멤버를 미리 선택**  
 이 옵션을 선택 하면 최근에 통합된 개발 환경 \(IDE\)의 현재 세션 동안 자동 개체 이름 완성 팝업 멤버 목록 상자에서 선택한 구성원 IntelliSense을 pre\-selects.  가장 최근에 사용된 멤버 기록은 IDE의 각 세션 사이에 지워집니다.  자세한 내용은 [가장 최근에 사용한 멤버를 위한 IntelliSense](../../misc/intellisense-for-most-recently-used-members.md)를 참조하십시오.  
  
## 참고 항목  
 [옵션 대화 상자, 환경, 일반](../../ide/reference/general-environment-options-dialog-box.md)   
 [XML 문서 주석](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [IntelliSense 사용](../../ide/using-intellisense.md)
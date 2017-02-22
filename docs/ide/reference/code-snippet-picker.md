---
title: "코드 조각 선택 | Microsoft Docs"
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
  - "vs.expansionpicker"
helpviewer_keywords: 
  - "코드 조각 선택"
  - "코드 조각, 코드 조각 선택"
  - "IntelliSense 코드 조각, 코드 조각 선택"
ms.assetid: f0862d48-fbbc-4cfe-b228-24492d5c89c4
caps.latest.revision: 25
caps.handback.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 코드 조각 선택
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코드 편집기는 미리 만들어진 코드 블록을 몇 번의 마우스 클릭으로 활성 문서에 삽입할 수 있도록 하는 **코드 조각 선택**을 제공합니다.  
  
 **코드 조각 선택**을 표시하는 프로시저는 사용하는 언어에 따라 달라집니다.  
  
-   [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] \- 코드 편집기의 원하는 위치에서 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입**을 선택합니다.  
  
-   [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] \- 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] \- **코드 조각 선택**을 사용할 수 없습니다.  
  
-   Visual F\# \- **코드 조각 선택**을 사용할 수 없습니다.  
  
-   [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] \- 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   XML \- 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   HTML \- 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   코드 편집기의 원하는 위치에서 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 표시한 다음 **코드 조각 삽입**을 선택합니다.  
  
 대부분의 Visual Studio 개발 언어에서 사용할 수는  **코드 조각 관리자** 폴더에 추가 하는  **폴더 목록** 는  **코드 조각 선택** XML 코드 조각 파일을 검색 합니다.  또한 사용자 고유의 조각을 만들어 목록에 추가할 수도 있습니다.  자세한 내용은 [연습: 코드 조각 만들기](../../ide/walkthrough-creating-a-code-snippet.md)를 참조하십시오.  
  
## UI 요소 목록  
 항목 이름  
 **항목 목록**에서 선택된 항목의 이름을 표시하는 편집 가능한 텍스트 필드입니다.  원하는 항목에 대해 증분 검색을 수행하려면 이 필드에 이름의 일부를 입력하고  원하는 항목이 **항목 목록**에서 선택될 때까지 문자를 계속 추가합니다.  
  
 항목 목록  
 삽입할 수 있는 코드 조각 목록 또는 코드 조각을 포함하고 있는 폴더 목록입니다.  코드 조각을 삽입하거나 폴더를 확장하려면 원하는 항목을 선택하고 Enter 키를 누릅니다.  
  
## 참고 항목  
 [코드 조각을 사용하는 방법에 대한 유용한 정보](../../ide/best-practices-for-using-code-snippets.md)   
 [Visual Basic IntelliSense Code Snippets](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
 [코드에 책갈피 설정](../../ide/setting-bookmarks-in-code.md)   
 [방법: 코드 감싸기 코드 조각 사용](../../ide/how-to-use-surround-with-code-snippets.md)
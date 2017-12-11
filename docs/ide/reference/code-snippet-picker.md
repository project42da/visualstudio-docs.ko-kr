---
title: "코드 조각 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.expansionpicker
helpviewer_keywords:
- Code Snippet Picker
- IntelliSense code snippets, Code Snippet Picker
- code snippets, Code Snippet Picker
ms.assetid: f0862d48-fbbc-4cfe-b228-24492d5c89c4
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 58f419d52d2d89f998f64e236cfc1f0053c9cfd1
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="code-snippet-picker"></a>코드 조각 선택
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 코드 편집기는 사용자가 몇 번의 마우스 클릭으로 현재 문서에 미리 만들어진 코드 블록을 삽입할 수 있는 **코드 조각 선택**을 제공합니다.  
  
 **코드 조각 선택**을 표시하는 프로시저는 사용 중인 언어에 따라 달라집니다.  
  
-   [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입**을 선택합니다.  
  
-   [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] - **코드 조각 선택**을 사용할 수 없습니다.  
  
-   Visual F# - **코드 조각 선택**을 사용할 수 없습니다.  
  
-   [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   XML - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   HTML - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입** 또는 **코드 감싸기**를 클릭합니다.  
  
-   SQL - 코드 편집기에서 원하는 위치를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시하고 **조각 삽입**을 클릭합니다.  
  
대부분의 Visual Studio 개발 언어에서 **코드 조각 관리자**를 사용하여 **코드 조각 선택**이 XML 코드 조각 파일을 검사하는 **폴더 목록**에 폴더를 추가할 수 있습니다. 또한 사용자 고유의 조각을 만들어 목록에 추가할 수 있습니다. 자세한 내용은 [연습: 코드 조각 만들기](../../ide/walkthrough-creating-a-code-snippet.md)를 참조하세요.  
  
## <a name="uielement-list"></a>UI 요소 목록  
항목 이름  
**항목 목록**에서 선택한 항목의 이름을 표시하는 편집 가능한 텍스트 필드입니다. 원하는 항목에 대한 증분 검색을 수행하려면 이 필드에 해당 이름을 입력하기 시작합니다. **항목 목록**에서 원하는 항목이 선택될 때까지 문자를 계속 추가합니다.  
  
항목 목록  
삽입할 수 있는 코드 조각의 목록 또는 코드 조각을 포함하는 폴더의 목록입니다. 코드 조각을 삽입하거나 폴더를 확장하려면 원하는 항목을 선택하고 Enter 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
[코드 조각 사용에 대한 모범 사례](../../ide/best-practices-for-using-code-snippets.md)   
[Visual Basic IntelliSense 코드 조각](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
[코드에 책갈피 설정](../../ide/setting-bookmarks-in-code.md)   
[방법: 코드 감싸기 코드 조각 사용](../../ide/how-to-use-surround-with-code-snippets.md)
---
title: "Visual Basic 관련 IntelliSense | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IntelliSense[Visual Basic]"
  - "IntelliSense[Visual Studio], Visual Basic"
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# Visual Basic 관련 IntelliSense
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Basic 소스 코드 편집기에서는 다음과 같은 IntelliSense 기능을 사용할 수 있습니다.  
  
-   구문 팁  
  
     구문 팁은 입력 중인 문의 구문을 표시하고  [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) 같은 문에 유용합니다.  
  
## 자동 완성  
  
-   다양한 키워드에 대한 완성  
  
     예를 들어, `goto` 및 공백을 입력하면 IntelliSense는 정의된 레이블 목록을 드롭다운 메뉴에 표시합니다.  기타 지원되는 키워드로는 `Exit`, `Implements`, `Option` 및 `Declare`가 있습니다.  
  
-   `Enum` 및 `Boolean`에 대한 완성  
  
     문이 열거형 멤버를 참조하는 경우 IntelliSense는 해당 `Enum` 멤버의 목록을 표시합니다.  문이 `Boolean`을 참조하는 경우 IntelliSense는 true\-false 드롭다운 메뉴를 표시합니다.  
  
 **Visual Basic** 폴더의 **일반** 속성 페이지에서 **멤버 목록 자동 표시**를 선택 취소하면 완성 기능을 기본적으로 설정 해제할 수 있습니다.  
  
 구성원 목록, 단어 자동 완성 또는 ALT \+ 오른쪽 화살표를 호출 하 여 완성을 수동으로 실행할 수 있습니다.  자세한 내용은 [IntelliSense 사용](../ide/using-intellisense.md)을 참조하십시오.  
  
## 영역 내 IntelliSense  
 영역 내 IntelliSense는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 통해 응용 프로그램을 배포해야 하고 부분 신뢰 설정의 제약을 받는 Visual Basic 개발자를 지원합니다.  이 기능을 사용하여 다음 작업을 할 수 있습니다.  
  
-   응용 프로그램을 실행하는 데 필요한 사용 권한을 선택할 수 있습니다.  
  
-   선택된 영역의 API는 멤버 목록에 사용할 수 있음으로 표시하고, 추가 권한이 필요한 API는 사용할 수 없음으로 표시합니다.  
  
 자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)을 참조하십시오.  
  
## 참고 항목  
 [IntelliSense 사용](../ide/using-intellisense.md)
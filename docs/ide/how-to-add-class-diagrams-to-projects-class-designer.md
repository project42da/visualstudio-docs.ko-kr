---
title: "How to: Add Class Diagrams to Projects (Class Designer) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "class diagrams, creating"
  - "Class Designer [Visual Studio], opening"
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
caps.latest.revision: 39
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# How to: Add Class Diagrams to Projects (Class Designer)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스와 기타 형식을 디자인, 편집 및 리팩터링하려면 Visual C\# .NET, Visual Basic .NET 또는 C\+\+ 프로젝트에 클래스 다이어그램을 추가합니다.  프로젝트에서 각기 다른 코드 부분을 표시하려면 여러 클래스 다이어그램을 프로젝트에 추가합니다.  
  
 여러 앱 간에 코드를 공유하는 프로젝트에서는 클래스 다이어그램을 만들 수 없습니다.  UML 클래스 다이어그램을 만들려면 [UML 모델링 프로젝트 및 다이어그램 만들기](../modeling/create-uml-modeling-projects-and-diagrams.md)를 참조하세요.  
  
### 프로젝트에 빈 클래스 다이어그램을 추가하려면  
  
1.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭합니다.  그 다음 **새 항목 추가** 또는 **추가**, **새 항목**을 선택합니다.  
  
2.  템플릿 목록에서 **클래스 다이어그램**을 선택합니다.  Visual C\+\+ 프로젝트의 경우 **템플릿**, 그 다음 **유틸리티**에서 이 템플릿을 찾습니다.  
  
     클래스 디자이너에 클래스 다이어그램이 열립니다. 이 다이어그램은 솔루션 탐색기에서 프로젝트 계층 구조에 확장명이 .cd인 파일로 나타납니다.  클래스 디자이너 도구 상자를 사용하여 도형과 선을 다이어그램으로 끌어 옵니다.  
  
3.  여러 클래스 다이어그램을 추가하려면 이 절차의 단계를 반복합니다.  
  
### 기존 형식을 기반으로 클래스 다이어그램을 추가하려면  
  
1.  솔루션 탐색기에서 클래스 파일 컨텍스트 메뉴를 연 다음 **클래스 다이어그램 보기**를 선택합니다.  
  
     또는  
  
     **클래스 뷰**에서 네임스페이스 또는 형식 컨텍스트 메뉴를 연 다음 **클래스 다이어그램 보기**를 선택합니다.  
  
### 클래스 다이어그램에 전체 프로젝트의 내용을 표시하려면  
  
1.  솔루션 탐색기나 클래스 뷰에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **보기**를 선택한 다음 **클래스 다이어그램 보기**를 선택합니다.  
  
     자동으로 채워진 클래스 다이어그램이 만들어집니다.  
  
## 참고 항목  
 [How to: Create Types by using Class Designer](../ide/how-to-create-types-by-using-class-designer.md)   
 [How to: View Existing Types \(Class Designer\)](../ide/how-to-view-existing-types-class-designer.md)   
 [Designing Classes and Types \(Class Designer\)](../ide/designing-classes-and-types-class-designer.md)   
 [Viewing Types and Relationships \(Class Designer\)](../ide/viewing-types-and-relationships-class-designer.md)   
 [Working with Class Diagrams \(Class Designer\)](../ide/working-with-class-diagrams-class-designer.md)
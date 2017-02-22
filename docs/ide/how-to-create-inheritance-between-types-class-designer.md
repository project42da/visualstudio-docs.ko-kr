---
title: "How to: Create Inheritance Between Types (Class Designer) | Microsoft Docs"
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
  - "vs.classdesigner.inheritanceline"
helpviewer_keywords: 
  - "inheritance, relationship defining"
  - "relationships, defining inheritance"
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: 30
caps.handback.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# How to: Create Inheritance Between Types (Class Designer)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스 디자이너를 사용하여 클래스 다이어그램의 두 형식 간에 상속 관계를 만들려면 기본 형식을 하나 이상의 파생 형식과 연결합니다.  두 클래스, 클래스와 인터페이스 또는 두 인터페이스 간에 상속 관계를 적용할 수 있습니다.  
  
### 형식 간에 상속을 만들려면  
  
1.  솔루션 탐색기의 프로젝트에서 클래스 다이어그램 파일\(.cd\)을 엽니다.  
  
     클래스 다이어그램이 없으면 새로 만듭니다.  [How to: Add Class Diagrams to Projects \(Class Designer\)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)을 참조하십시오.  
  
2.  **도구 상자**의 **클래스 디자이너**에서 **상속**을 클릭합니다.  
  
3.  클래스 다이어그램에서 다음 항목부터 시작하여 원하는 형식 간에 상속 선을 그립니다.  
  
    -   파생 클래스에서 기본 클래스로  
  
    -   구현할 클래스에서 구현된 인터페이스로  
  
    -   확장할 인터페이스에서 확장된 인터페이스로  
  
4.  원하는 경우 제네릭 형식에서 파생된 형식이 있으면 상속 선을 클릭하고  **속성** 창에서 제네릭 형식에 대해 원하는 형식과 일치하도록 **형식 인수** 속성을 설정합니다.  
  
    > [!NOTE]
    >  부모 추상 클래스에 추상 멤버가 하나 이상 포함되어 있으면 모든 추상 멤버가 비추상 상속 클래스로 구현됩니다.  [Implementing Abstract Base Classes](../ide/refactoring-classes-and-types-class-designer.md#ImplementingAbstractBaseClasses)을 참조하십시오.  
    >   
    >  기존 제네릭 형식을 시각화할 수는 있지만 새 제네릭 형식을 만들 수는 없습니다.  또한 기존 제네릭 형식의 형식 매개 변수를 변경할 수도 없습니다.  
  
## 참고 항목  
 [상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [How to: View Inheritance Between Types \(Class Designer\)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Visual C\+\+ Classes in Class Designer](../ide/visual-cpp-classes-in-class-designer.md)
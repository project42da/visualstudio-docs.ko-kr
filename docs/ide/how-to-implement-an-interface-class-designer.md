---
title: "How to: Implement an Interface (Class Designer) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "interfaces [Visual Studio], implementing"
  - "interfaces [Visual Studio]"
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 16
caps.handback.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# How to: Implement an Interface (Class Designer)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스 디자이너에서 인터페이스 메서드에 대한 코드를 제공하는 클래스에 인터페이스를 연결하여 클래스 다이어그램에 인터페이스를 구현할 수 있습니다.  클래스 디자이너는 인터페이스 구현을 생성하고 인터페이스와 클래스 간의 관계를 상속 관계로 표시합니다.  인터페이스와 클래스 간에 상속 선을 그리거나 클래스 뷰에서 상속을 끌어 인터페이스를 구현할 수 있습니다.  
  
> [!TIP]
>  다른 형식을 만들 때와 같은 방법으로 인터페이스를 만들 수 있습니다.  인터페이스가 존재하지만 클래스 다이어그램에 나타나지 않으면 먼저 이를 표시합니다.  자세한 내용은 [How to: Create Types by using Class Designer](../ide/how-to-create-types-by-using-class-designer.md) 및 [How to: View Existing Types \(Class Designer\)](../ide/how-to-view-existing-types-class-designer.md)를 참조하십시오.  
  
### 상속 선을 그려 인터페이스를 구현하려면  
  
1.  클래스 다이어그램에서 인터페이스와 인터페이스를 구현할 클래스를 표시합니다.  
  
2.  클래스에서 인터페이스로 상속 선을 그립니다.  
  
     클래스에 롤리팝이 연결되어 나타나고 인터페이스 이름으로 된 레이블이 상속 관계를 식별합니다.  모든 인터페이스 멤버에 대한 스텁이 생성됩니다.  
  
 자세한 내용은 [How to: Create Inheritance Between Types \(Class Designer\)](../ide/how-to-create-inheritance-between-types-class-designer.md)를 참조하십시오.  
  
### 클래스 뷰 창에서 인터페이스를 구현하려면  
  
1.  클래스 다이어그램에서 인터페이스를 구현할 클래스를 표시합니다.  
  
2.  클래스 뷰를 열고 인터페이스를 찾습니다.  
  
    > [!TIP]
    >  클래스 뷰가 열려 있지 않으면 **보기** 메뉴에서 클래스 뷰를 엽니다.  클래스 뷰에 대한 자세한 내용은 [Viewing Classes and Their Members](http://msdn.microsoft.com/ko-kr/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333)를 참조하십시오.  
  
3.  인터페이스 노드를 다이어그램의 클래스 모양으로 끌어 놓습니다.  
  
     클래스에 롤리팝이 연결되어 나타나고 인터페이스 이름으로 된 레이블이 상속 관계를 식별합니다.  모든 인터페이스 멤버에 대한 스텁이 생성되고 인터페이스가 구현됩니다.  
  
## 참고 항목  
 [How to: Create Types by using Class Designer](../ide/how-to-create-types-by-using-class-designer.md)   
 [How to: View Existing Types \(Class Designer\)](../ide/how-to-view-existing-types-class-designer.md)   
 [How to: Create Inheritance Between Types \(Class Designer\)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Refactoring Classes and Types \(Class Designer\)](../ide/refactoring-classes-and-types-class-designer.md)
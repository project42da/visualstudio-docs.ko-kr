---
title: "How to: Change Between Member Notation and Association Notation (Class Designer) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "notation, member"
  - "association notation"
  - "member notation"
  - "notation, association"
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# How to: Change Between Member Notation and Association Notation (Class Designer)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스 디자이너에서 클래스 다이어그램이 두 형식 간의 연결 관계를 나타내는 방법을 멤버 표시에서 연결 표시로 또는 그 반대로 변경할 수 있습니다.  멤버를 연결 선으로 표시하면 형식의 연결 관계를 시각적으로 쉽게 확인할 수 있습니다.  
  
> [!NOTE]
>  연결 관계는 멤버 속성 또는 필드로 나타낼 수 있습니다.  멤버 표기법을 연결 표기법으로 변경하려면 한 형식이 다른 형식의 멤버를 포함해야 하고,  연결 표기법을 멤버 표기법으로 변경하려면 두 형식이 연결 선으로 연결되어 있어야 합니다.  자세한 내용은 [How to: Create Associations Between Types \(Class Designer\)](../ide/how-to-create-associations-between-types-class-designer.md)를 참조하십시오.  프로젝트에 여러 클래스 다이어그램이 포함되어 있는 경우 한 다이어그램에서 연결 관계를 표시하는 방법을 변경하면 해당 다이어그램에만 영향을 줍니다.  다른 다이어그램의 연결 관계 표시 방법을 변경하려면 해당 다이어그램을 열거나 표시한 후 다음 단계를 수행합니다.  
  
### 멤버 표기법에서 연결 표기법으로 변경하려면  
  
1.  솔루션 탐색기의 프로젝트 노드에서 클래스 다이어그램 파일\(.cd\)을 엽니다.  
  
2.  클래스 다이어그램의 형식 모양에서 해당 연결을 나타내는 필드나 멤버 속성을 마우스 오른쪽 단추로 클릭한 후에 **형식 연결로 표시**를 선택합니다.  
  
    > [!TIP]
    >  형식 모양에 속성이나 필드가 보이지 않으면 모양의 구획이 축소된 것일 수도 있습니다.  형식 모양을 확장하려면 구획 이름을 두 번 클릭하거나 형식 모양을 마우스 오른쪽 단추로 클릭한 후에 **확장**을 선택합니다.  
  
     멤버가 형식 모양의 구획에서 사라지고 두 형식을 연결하는 연결 선이 나타납니다.  속성이나 필드의 이름이 연결 선의 레이블이 됩니다.  
  
### 연결 표기법을 멤버 표기법으로 변경하려면  
  
-   클래스 다이어그램에서 연결 선을 마우스 오른쪽 단추로 클릭한 후에 **속성으로 표시** 또는 **필드로 표시**를 선택합니다.  
  
     연결 선이 사라지고 다이어그램에서 형식 모양의 해당 구획에 속성이 표시됩니다.  
  
## 참고 항목  
 [How to: Create Inheritance Between Types \(Class Designer\)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [How to: View Inheritance Between Types \(Class Designer\)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [Viewing Types and Relationships \(Class Designer\)](../ide/viewing-types-and-relationships-class-designer.md)   
 [How to: Visualize a Collection Association \(Class Designer\)](../ide/how-to-visualize-a-collection-association-class-designer.md)
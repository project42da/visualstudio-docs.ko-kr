---
title: "방법: 형식 간의 상속 만들기(클래스 디자이너) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: 30
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: bd4969c26d1cc0043945189bd4da3acbf5792107
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---
# <a name="how-to-create-inheritance-between-types-class-designer"></a>방법: 형식 간의 상속 만들기(클래스 디자이너)
클래스 디자이너를 사용하여 클래스 다이어그램의 두 형식 간에 상속 관계를 만들려면 기본 형식을 하나 이상의 파생 형식과 연결합니다. 두 클래스, 클래스와 인터페이스 또는 두 인터페이스 간에 상속 관계를 적용할 수 있습니다.  
  
### <a name="to-create-an-inheritance-between-types"></a>형식 간에 상속을 만들려면  
  
1.  솔루션 탐색기의 프로젝트에서 클래스 다이어그램 파일(.cd)을 엽니다.  
  
     클래스 다이어그램이 없으면 새로 만듭니다. [How to: Add Class Diagrams to Projects (Class Designer)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)을 참조하세요.  
  
2.  **도구 상자**의 **클래스 디자이너**에서 **상속**을 클릭합니다.  
  
3.  클래스 다이어그램에서 다음 항목부터 시작하여 원하는 형식 간에 상속 선을 그립니다.  
  
    -   파생 클래스에서 기본 클래스로  
  
    -   구현할 클래스에서 구현된 인터페이스로  
  
    -   확장할 인터페이스에서 확장된 인터페이스로  
  
4.  원하는 경우 제네릭 형식에서 파생된 형식이 있으면 상속 선을 클릭하고 **속성** 창에서 제네릭 형식에 대해 원하는 형식과 일치하도록 **형식 인수** 속성을 설정합니다.  
  
    > [!NOTE]
    >  부모 추상 클래스에 추상 멤버가 하나 이상 포함되어 있으면 모든 추상 멤버가 비추상 상속 클래스로 구현됩니다.  
    >   
    >  기존 제네릭 형식을 시각화할 수는 있지만 새 제네릭 형식을 만들 수는 없습니다. 또한 기존 제네릭 형식의 형식 매개 변수를 변경할 수도 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)   
 [상속 기본 사항](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [방법: 형식 간의 상속 보기(클래스 디자이너)](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [클래스 디자이너의 Visual C++ 클래스](../ide/visual-cpp-classes-in-class-designer.md)

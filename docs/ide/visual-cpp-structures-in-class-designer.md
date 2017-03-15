---
title: "Visual C++ Structures in Class Designer | Microsoft Docs"
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
  - "Class Designer [Visual Studio], structures"
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Visual C++ Structures in Class Designer
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

클래스 디자이너에서는 `struct` 키워드로 선언된 C\+\+ 구조체가 지원됩니다.  예를 들면 다음과 같습니다.  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 `struct` 형식 사용에 대한 자세한 내용은 [struct](/visual-cpp/cpp/struct-cpp)를 참조하십시오.  
  
 클래스 다이어그램에서 C\+\+ 구조체 모양은 레이블이 **구조체**이고 모퉁이가 둥근 것이 아니라 사각형이라는 점을 제외하고는 클래스 모양과 생김새 및 동작이 비슷합니다.  
  
|코드 요소|클래스 디자이너 뷰|  
|-----------|----------------|  
|`struct StructureName {};`|**StructureName**<br /><br /> 구조체|  
  
## 참고 항목  
 [Working with Visual C\+\+ Code \(Class Designer\)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [클래스 및 구조체](/visual-cpp/cpp/classes-and-structs-cpp)   
 [struct](/visual-cpp/cpp/struct-cpp)
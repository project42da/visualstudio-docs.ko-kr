---
title: "&#39;Set&#39; 매개 변수는 포함하는 속성과 형식이 같아야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31064"
  - "bc31064"
helpviewer_keywords: 
  - "BC31064"
ms.assetid: f0b8310d-68a1-4989-ac64-03b1861528ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Set&#39; 매개 변수는 포함하는 속성과 형식이 같아야 합니다.
`Set` 속성 프로시저에 대한 매개 변수에는 자신이 속한 속성과 다른 형식이 있습니다.  
  
 **오류 ID:** BC31064  
  
### 이 오류를 해결하려면  
  
-   매개 변수의 데이터 형식을 `Set`로 변경하여 속성에 대한 데이터 형식과 일치시킵니다. 예:  
  
    ```  
    Class Class1 ' Declare a local variable to hold the property value. Private Fval As Integer Property F() As Integer Get Return Fval End Get Set(ByVal Value As Integer) Fval = Value End Set End Property End Class  
    ```  
  
## 참고 항목  
 [빌드에 없음: 방법: 클래스에 필드 및 속성을 추가합니다.](http://msdn.microsoft.com/ko-kr/ae53f61b-3abc-413e-8931-703c5f5e8fc2)   
 [Property 프로시저](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)   
 [빌드에 없음: 속성 및 속성 프로시저](http://msdn.microsoft.com/ko-kr/23e2a1ec-7e9d-4109-8940-c703d981077b)
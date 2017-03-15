---
title: "반환 형식에 액세스할 수 없으므로 이 컨텍스트에서 &#39;&lt;methodname&gt;&#39;에 액세스할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36665"
  - "vbc36666"
  - "bc36666"
  - "vbc36665"
helpviewer_keywords: 
  - "BC36666"
  - "BC36665"
ms.assetid: 8f29eb7e-351f-486c-9d1f-3556cc11b7c5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 반환 형식에 액세스할 수 없으므로 이 컨텍스트에서 &#39;&lt;methodname&gt;&#39;에 액세스할 수 없습니다.
호출 문에서 액세스할 수 없는 반환 형식을 가진 함수를 호출했습니다. 예를 들어 다음 코드에서 반환 형식인 `PrivateType`이 `TestClass` 클래스에서 `Private` 액세스 한정자를 사용하여 선언되므로 `Main`에서 `PublicMethod`로의 호출은 실패합니다. 따라서 `PrivateType`을 액세스할 수 있는 컨텍스트는 `TestClass`로 제한됩니다.  
  
```vb#  
Class TestClass  
  
    Dim pT As New PrivateType  
  
    Private Class PrivateType  
    End Class  
  
    '' A corresponding error is returned in this line: 'PublicMethod   
    '' cannot expose 'PrivateType' in namespace 'ConsoleApplication1'   
    '' through class 'TestClass'.  
    'Public Function PublicMethod() As PrivateType  
    '    Return Nothing  
    'End Function  
  
End Class  
  
Module Module1  
  
    Sub Main()  
  
        Dim tc As TestClass  
        '' This error occurs here, because the data type returned by   
        '' PublicMethod()is declared Private in class TestClass and   
        '' cannot be accessed from here.  
        'Console.WriteLine(tc.PublicMethod())  
  
    End Sub  
  
End Module  
```  
  
 **오류 ID:** BC36665 및 BC36666  
  
### 이 오류를 해결하려면  
  
-   형식 정의에 액세스할 수 있는 경우 액세스 한정자를 `Private`에서 `Public`으로 변경합니다.  
  
-   액세스 권한이 있는 경우 함수의 반환 형식을 변경합니다.  
  
-   액세스할 수 있는 형식을 반환하는 메서드 또는 확장 메서드를 작성합니다.  
  
## 참고 항목  
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)
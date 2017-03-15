---
title: "&#39;Optional&#39;은 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc36553"
  - "vbc36553"
helpviewer_keywords: 
  - "BC36553"
ms.assetid: 8ea0b90c-f155-47a9-988b-5b8009b510af
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Optional&#39;은 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다.
'Optional'은 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다. 첫 번째 매개 변수는 확장할 형식을 지정합니다.  
  
 확장 메서드의 첫 번째 매개 변수는 메서드가 확장하는 데이터 형식을 지정합니다. 메서드가 확장되면 첫 번째 매개 변수가 메서드를 호출하는 데이터 형식의 인스턴스에 바인딩됩니다. 따라서 첫 번째 매개 변수는 필수이며 선택 사항이 될 수 없습니다.  
  
 이 제한은 첫 번째 매개 변수에만 적용됩니다. 다른 매개 변수는 다른 메서드의 동일한 규칙에 따라 선택 사항이 될 수도 있습니다. 자세한 내용은 [Parameter List](/dotnet/visual-basic/language-reference/statements/parameter-list)을 참조하세요.  
  
 **오류 ID:** BC36553  
  
### 이 오류를 해결하려면  
  
-   현재 첫 번째 매개 변수에서 확장 중인 데이터 형식을 지정하도록 하려면 `Optional` 키워드를 제거합니다.  
  
-   현재 첫 번째 매개 변수가 메서드에 대한 표준 매개 변수이고 이 매개 변수에서 확장 중인 데이터 형식을 나타내지 않으려는 경우 첫 번째 매개 변수를 새로 추가합니다.  
  
## 예제  
 다음 예제에서 첫 번째 매개 변수는 `Print` 메서드가 `String` 데이터 형식을 확장한다는 것을 나타냅니다. 따라서 선택 사항일 수 없습니다.  
  
```  
<Extension()> Public Sub Print (ByVal str As String) Console.WriteLine(str) End Sub  
```  
  
 확장 메서드가 다음과 같이 호출되는 경우 메서드의 `str` 매개 변수는 `Print`를 호출하는 `String`의 인스턴스인 `greeting`에 바인딩됩니다. 컴파일러에서는 `greeting`을 확장 메서드 `Print`의 인수로 사용합니다.  
  
```  
Dim greeting As String = "Hello" greeting.Print()  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [방법: 프로시저의 선택적 매개 변수 정의\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0b32b312-0da0-489b-96ad-7dcb1f1f8f88)   
 [Optional Parameters](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)
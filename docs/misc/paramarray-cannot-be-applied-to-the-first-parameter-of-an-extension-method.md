---
title: "&#39;ParamArray&#39;는 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36554"
  - "bc36554"
helpviewer_keywords: 
  - "BC36554"
ms.assetid: 0778a854-246f-4c2b-943d-ea8883b3aa6f
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ParamArray&#39;는 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다.
'ParamArray'는 확장 메서드의 첫 번째 매개 변수에 적용할 수 없습니다. 첫 번째 매개 변수는 확장할 형식을 지정합니다.  
  
 확장 메서드의 첫 번째 매개 변수는 메서드가 확장하는 데이터 형식을 지정합니다. 따라서 첫 번째 매개 변수는 필수이며 선택 사항이 될 수 없습니다. 매개 변수 배열은 자동으로 선택 사항이므로 확장 메서드의 첫 번째 인수로 사용할 수 없습니다.  
  
> [!NOTE]
>  메서드가 실행되면 메서드를 호출하는 확장 데이터 형식의 인스턴스가 메서드의 첫 번째 매개 변수에 대한 인수가 됩니다. 예를 들어 `greeting.Print()`의 `greeting` 인스턴스는 확장 메서드 `Public Sub Print (ByVal str As String)`의 첫 번째 매개 변수 `str`에 대한 인수입니다.  
  
 **오류 ID:** BC36554  
  
### 이 오류를 해결하려면  
  
-   매개 변수 배열에서 확장하려는 데이터 형식을 지정하지 않는 경우 이 형식을 지정하는 새로운 첫 번째 매개 변수를 추가합니다.  
  
    ```  
    <Extension()> Public Sub AddTo(ByRef str As String, ByVal ParamArray addOns() As String) ' Concatenate the strings in addOns to str. End Sub  
    ```  
  
-   매개 변수 배열에서 확장하려는 데이터 형식을 지정하는 경우 매개 변수 배열이 아니라 인수가 필요한 일반 배열로 변경하는 것이 좋습니다. 일반 배열은 확장할 수 있습니다.  
  
    ```  
    <Extension()> Public Function Sum(ByVal ints() As Integer) As Integer Dim total As Integer = 0 For Each i As Integer In ints total = total + i Next i Return total End Function  
    ```  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Parameter Arrays](/dotnet/visual-basic/programming-guide/language-features/procedures/parameter-arrays)   
 [Optional Parameters](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)
---
title: "확장 메서드 &#39;&lt;methodname&gt;&#39;에 충족될 수 없는 형식 제약 조건이 있습니다. | Microsoft Docs"
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
  - "bc36561"
  - "vbc36561"
helpviewer_keywords: 
  - "BC36561"
ms.assetid: ff42d6e9-611b-407d-a269-f268b36ed277
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 확장 메서드 &#39;&lt;methodname&gt;&#39;에 충족될 수 없는 형식 제약 조건이 있습니다.
이 메서드의 형식 매개 변수는 형식 제약 조건이 충족될 수 없도록 하는 방식으로 상호 작용합니다. 다음은 확장 메서드의 예입니다.  
  
```  
'' Not valid. '<Extension()> _ 'Sub extensionExample(Of T As U, U)(ByVal para1 As T, ByVal para2 As U) 'End Sub  
```  
  
 메서드가 확장 메서드이므로 컴파일러에서는 메서드 선언, `para1` 및 해당 매개 변수에 대해 전달되는 인수의 첫 번째 매개 변수만 기반으로 하는 메서드를 확장하는 데이터 형식을 결정할 수 있어야 합니다. 첫 번째 매개 변수가 제네릭 형식 매개 변수 `para1 as T`를 참조할 때 제네릭 매개 변수의 제약 조건은 메서드가 적용되는 형식 집합을 제한합니다.  
  
 확장 메서드의 적용 가능성은 첫 번째 매개 변수\(다음 코드의 `arg1`\)에 제공되는 인수로 결정됩니다.  
  
 `'' Not valid.`  
  
 `'arg1.extensionExample(arg2)`  
  
 첫 번째 인수  `arg1`만 확인하여 첫 번째 매개 변수 `para1`이 참조하는 모든 제네릭 형식 매개 변수에 대한 제약 조건을 확인할 수 있어야 합니다.`extensionExample`에서 확장되는 형식 집합을 첫 번째 매개 변수만으로 확인할 수 없습니다. 형식 매개 변수 `T`는 `para1`이 참조하지 않는 형식 매개 변수 `U`로 제한되며 `arg1`에서 유추할 수 없습니다. 따라서 모든 가능한 형식에 대한 메서드 적용 가능성은 확인할 수 없으며 메서드를 호출할 수 없습니다.  
  
 **오류 ID:** BC36561  
  
### 이 오류를 해결하려면  
  
-   형식 선언을 변경하여 형식 간 상호 종속성을 제거합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)
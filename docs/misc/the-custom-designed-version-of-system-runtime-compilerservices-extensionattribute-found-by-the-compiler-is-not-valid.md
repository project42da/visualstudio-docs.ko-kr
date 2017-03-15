---
title: "컴파일러에서 검색한 &#39;System.Runtime.CompilerServices.ExtensionAttribute&#39;의 사용자 지정 디자인 버전이 유효하지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36558"
  - "bc36558"
helpviewer_keywords: 
  - "BC36558"
ms.assetid: f47d310a-95fd-4340-bda2-21262c217dbb
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 컴파일러에서 검색한 &#39;System.Runtime.CompilerServices.ExtensionAttribute&#39;의 사용자 지정 디자인 버전이 유효하지 않습니다.
컴파일러에서 검색한 'System.Runtime.CompilerServices.ExtensionAttribute'의 사용자 지정 디자인 버전이 유효하지 않습니다. 해당 특성 사용 플래그가 어셈블리, 클래스 및 메서드를 허용하도록 설정되어야 합니다.  
  
 컴파일러에서 검색한 <xref:System.Runtime.CompilerServices.ExtensionAttribute?displayProperty=fullName>의 사용자 지정 디자인 버전이 어셈블리, 메서드 및 클래스에 특성을 적용하기 위한 해당 특성 사용 플래그를 설정하지 않았습니다. 적어도 이 세 개의 프로그램 요소는 적용해야 합니다.  
  
 **오류 ID:** BC36558  
  
### 이 오류를 해결하려면  
  
-   최소한 어셈블리, 메서드 및 클래스에 적용할 특성을 사용하도록 하려면 다음 예제와 같이 특성 정의를 변경합니다.  
  
-   사용자 지정 디자인 버전 대신 <xref:System.Runtime.CompilerServices.ExtensionAttribute?displayProperty=fullName>를 사용합니다.  
  
## 예제  
 다음 예제에서는 `AttributeUsage` 특성을 사용하여 새 버전의 `ExtensionAttribute`가 적용할 수 있는 프로그램 요소를 지정합니다. 이 예제에서는 `AttributeTargets` 열거형의 세 멤버인 `Assembly`, `Class` 및 `Method`를 지정합니다. 이들 요소 중 하나를 생략하면 이 오류가 발생합니다.  
  
```  
Namespace System.Runtime.CompilerServices <AttributeUsage(AttributeTargets.Assembly Or _ AttributeTargets.Class Or AttributeTargets.Method)> Class ExtensionAttribute Inherits System.Attribute ' Definitions of methods, fields, and properties. End Class End Namespace  
```  
  
 또는 `ExtensionAttribute`에서 `AttributeTargets`의 `All` 멤버를 모든 프로그램 요소에 적용하는 것을 허용할 수 있습니다.  
  
```  
<AttributeUsage(AttributeTargets.All)>  
```  
  
 다음 코드와 같이 `AttributeUsage` 줄을 삭제하면 같은 결과를 얻을 수 있습니다.  
  
```  
Namespace System.Runtime.CompilerServices Class ExtensionAttribute Inherits System.Attribute ' Definitions of methods, fields, and properties. End Class End Namespace  
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [빌드에 없음: Visual Basic의 특성 개요](http://msdn.microsoft.com/ko-kr/0d0cff64-892d-4f57-83bd-bef388553d4f)   
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)   
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [빌드에 없음: 방법: 사용자 고유의 특성 정의](http://msdn.microsoft.com/ko-kr/039609c4-ec43-4f44-945f-aa3b5b535c6a)   
 [사용자 지정 특성 작성](../Topic/Writing%20Custom%20Attributes.md)
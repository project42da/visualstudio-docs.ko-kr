---
title: "두 개 이상의 형식이 가능하므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc36653"
  - "bc36653"
  - "vbc36650"
  - "bc36650"
helpviewer_keywords: 
  - "BC36650"
  - "BC36653"
ms.assetid: 79287e1f-7070-4a71-96d2-aee0a0c9d8bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 두 개 이상의 형식이 가능하므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
두 개 이상의 형식이 가능하므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 이 오류는 오버로드 확인에 실패한 경우에 발생합니다. 특정 오버로드 후보가 제거된 이유를 나타내는 하위 메시지로 발생합니다. 이 오류는 형식 유추를 적용하여 호출된 제네릭 프로시저의 형식 매개 변수에 대한 데이터 형식을 확인할 경우 컴파일러가 적어도 한 매개 변수의 가능한 데이터 형식을 둘 이상 찾는다고 설명합니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 자세한 내용과 예제를 보려면 [두 개 이상의 형식이 가능하므로 이 인수에서 '\<methodname\>' 메서드에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.](../misc/data-type-s-of-the-type-parameter-s-in-method-methodname-cannot-be-inferred-from-these-arguments-because-more-than-one-type-is-possible.md)을 참조하세요.  
  
 **오류 ID:** BC36653 및 BC36650  
  
## 참고 항목  
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)
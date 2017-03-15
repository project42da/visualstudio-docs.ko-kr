---
title: "동일한 형식으로 변환할 수 없으므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "vbc36659"
  - "bc36659"
  - "vbc36656"
  - "bc36656"
helpviewer_keywords: 
  - "BC36659"
  - "BC36656"
ms.assetid: 0aa809da-3b44-4d78-b3c5-0a148bdf7ce8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 동일한 형식으로 변환할 수 없으므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
동일한 형식으로 변환할 수 없으므로 이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 이 오류는 오버로드 확인에 실패한 경우에 발생합니다. 특정 오버로드 후보가 제거된 이유를 나타내는 하위 메시지로 발생합니다. 오류는 컴파일러에서 형식 유추를 사용하여 인수와 호환되는 형식 매개 변수의 데이터 형식을 찾을 수 없음을 설명합니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 자세한 내용과 예제를 보려면 [동일한 형식으로 변환할 수 없으므로 이 인수에서 '\<methodname\>' 메서드의 형식 매개 변수에 대한 데이터 형식을 유추할 수 없습니다.](../misc/data-type-s-of-the-type-parameter-s-in-method-methodname-cannot-be-inferred-from-these-arguments-because-they-do-not-convert-to-the-same-type.md)을 참조하세요.  
  
 **오류 ID:** BC36659 및 BC36656  
  
## 참고 항목  
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)
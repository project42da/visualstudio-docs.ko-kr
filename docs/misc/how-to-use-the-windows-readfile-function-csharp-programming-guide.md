---
title: "방법: Windows ReadFile 함수 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ReadFile 함수[C#]"
ms.assetid: 46bb53e0-a658-48c9-ae36-6720da7781c1
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "billchi"
manager: "douge"
---
# 방법: Windows ReadFile 함수 사용(C# 프로그래밍 가이드)
이 예제에서는 텍스트 파일을 읽고 표시하는 Windows `ReadFile` 함수를 보여 줍니다.  `ReadFile` 함수에는 `unsafe` 코드를 사용해야 합니다. 이 함수에는 포인터를 매개 변수로 사용해야 하기 때문입니다.  
  
 `Read` 함수로 전달된 바이트 배열은 관리되는 형식입니다.  따라서 CLR\(공용 언어 런타임\) 가비지 수집기에서는 배열이 사용한 메모리를 임의대로 다시 할당할 수 있습니다.  이를 방지하려면 [fixed](/dotnet/csharp/language-reference/keywords/fixed-statement)를 사용하여 메모리에 대한 포인터를 가져오고 가비지 수집기가 이를 옮기지 못하도록 표시해야 합니다.  `fixed` 블록의 끝에서 메모리가 자동으로 반환되어 가비지 수집을 통해 이동합니다.  
  
 이 기능을 *선언적 고정*이라고 합니다.  고정을 사용할 경우 `fixed` 블록에서 가비지 수집이 발생하는 매우 드문 경우 이외에는 오버헤드가 거의 없습니다.  하지만 고정으로 인해 전역 가비지 수집이 실행되는 동안 몇 가지 부작용이 나타날 수 있습니다.  예를 들어 가비지 수집기의 메모리 압축 기능은 고정된 버퍼 때문에 상당히 제한됩니다.  따라서 가능하면 고정을 사용하지 않는 것이 좋습니다.  
  
## 예제  
 [!code-cs[csProgGuidePointers#2](../misc/codesnippet/CSharp/how-to-use-the-windows-readfile-function-csharp-programming-guide_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](/dotnet/csharp/programming-guide/index)   
 [C\# 참조](/dotnet/csharp/language-reference/index)   
 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index)   
 [포인터 형식](/dotnet/csharp/programming-guide/unsafe-code-pointers/pointer-types)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)
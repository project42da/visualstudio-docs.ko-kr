---
title: "컴파일러 오류 CS0313 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0313"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0313"
ms.assetid: a0b0f2fb-e742-4df8-98bd-3bc068f0c71c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0313
제네릭 형식 또는 메서드 'type2'에서 'type1' 형식을 형식 매개 변수 'parameter name'으로 사용할 수 없습니다. nullable 형식 'type1'이 'type2'의 제약 조건을 만족하지 않습니다. nullable 형식은 인터페이스 제약 조건을 충족할 수 없습니다.  
  
 nullable 형식은 nullable이 아닌 상응 항목과 동일하지 않습니다. 아래에 있는 예제에서 `ImplStruct`는 `BaseInterface` 제약 조건을 충족하지만 `ImplStruct?`는 `Nullable<ImplStruct>`에서 `BaseInterface`를 구현하지 않기 때문에 충족하지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  아래에 있는 코드를 예제로 사용할 경우 한 가지 해결 방법은 `TestMethod` 호출의 첫 번째 형식 인수로 일반 `ImplStruct`를 지정하는 것입니다. 그런 다음 return 문에서 `Implstruct`의 nullable 버전을 만들도록 `TestMethod`를 수정합니다.  
  
    ```  
    return new Nullable<T>(t);  
    ```  
  
## 예제  
 다음 코드에서는 CS0313을 생성합니다.  
  
```  
// cs0313.cs public interface BaseInterface { } public struct ImplStruct : BaseInterface { } public class TestClass { public T? TestMethod<T, U>(T t) where T : struct, U { return t; } } public class NullableTest { public static void Run() { TestClass tc = new TestClass(); tc.TestMethod<ImplStruct?, BaseInterface>(new ImplStruct?()); // CS0313 } public static void Main() { } }  
```  
  
## 참고 항목  
 [nullable 형식](/dotnet/csharp/programming-guide/nullable-types/index)
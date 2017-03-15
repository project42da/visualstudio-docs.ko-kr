---
title: "컴파일러 오류 CS0011 | Microsoft Docs"
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
  - "CS0011"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0011"
ms.assetid: 892553d7-a516-4631-84cd-94db5722c90d
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0011
'type' 형식에서 참조하는 'assembly' 어셈블리의 'class' 인터페이스 또는 기본 클래스를 확인할 수 없습니다.  
  
 **\/reference**를 사용하여 파일에서 가져온 클래스가 클래스에서 파생되거나 찾을 수 없는 인터페이스를 구현합니다.**\/reference**를 사용한 컴파일에 필요한 DLL이 포함되지 않은 경우에도 발생할 수 있습니다.  
  
 자세한 내용은 [Add Reference Dialog Box](http://msdn.microsoft.com/ko-kr/2feb0fe2-0805-4cc9-8cba-b0315849dfb7) 및 [\/reference \(Import Metadata\)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)를 참조하세요.  
  
## 예제  
  
```  
// CS0011_1.cs // compile with: /target:library public class Outer { public class B { } }  
```  
  
## 예제  
 두 번째 파일은 이전 예제에서 만든 `B` 클래스에서 파생된 `C` 클래스를 정의하는 DLL을 만듭니다.  
  
```  
// CS0011_2.cs // compile with: /target:library /reference:CS0011_1.dll // post-build command: del /f CS0011_1.dll public class C : Outer.B {}  
```  
  
## 예제  
 세 번째 파일은 첫 번째 단계에서 만든 DLL을 대체하고 내부 클래스 `B`의 정의를 생략합니다.  
  
```  
// CS0011_3.cs // compile with: /target:library /out:cs0011_1.dll public class Outer {}  
```  
  
## 예제  
 마지막으로 네 번째 파일은 두 번째 예제에서 정의된 `C` 클래스\(`B` 클래스에서 파생되며 현재 없음\)를 참조합니다.  
  
 다음 샘플에서는 CS0011을 생성합니다.  
  
```  
// CS0011_4.cs // compile with: /reference:CS0011_1.dll /reference:CS0011_2.dll // CS0011 expected class M { public static void Main() { C c = new C(); } }  
```  
  
## 참고 항목  
 [Add Reference Dialog Box](http://msdn.microsoft.com/ko-kr/2feb0fe2-0805-4cc9-8cba-b0315849dfb7)   
 [\/reference \(Import Metadata\)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)
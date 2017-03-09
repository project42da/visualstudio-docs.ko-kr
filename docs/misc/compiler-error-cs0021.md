---
title: "컴파일러 오류 CS0021 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0021"
ms.assetid: 4eb5fa24-8261-4962-b36a-224be5074217
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0021
\[\]를 사용하는 인덱싱을 'type' 형식의 식에 적용할 수 없습니다.  
  
 [인덱서](/dotnet/csharp/programming-guide/indexers/index)를 지원하지 않는 데이터 형식의 인덱서를 통해 값에 액세스하려고 했습니다.  
  
 C\+\+ 어셈블리에서 인덱서를 사용하려고 하면 CS0021이 발생할 수 있습니다. 이 경우 `DefaultMember` 특성으로 C\+\+ 클래스를 데코레이팅하여 C\# 컴파일러에서 기본 인덱서를 알 수 있도록 합니다. 다음 샘플에서는 CS0021을 생성합니다.  
  
## 예제  
 이 파일은 오류를 생성하기 위해 `DefaultMember` 특성을 주석으로 처리하여 .dll 파일로 컴파일됩니다.  
  
```  
// CPP0021.cpp // compile with: /clr /LD using namespace System::Reflection; // Uncomment the following line to resolve //[DefaultMember("myItem")] public ref class MyClassMC { public: property int myItem[int] { int get(int i){  return 5; } void set(int i, int value) {} } };  
```  
  
## 예제  
 다음은 .dll 파일을 호출하는 C\# 파일입니다. 이 파일은 인덱서를 통해 클래스에 액세스하려고 하지만 사용할 기본 인덱서로 선언된 멤버가 없기 때문에 오류가 생성됩니다.  
  
```  
// CS0021.cs // compile with: /reference:CPP0021.dll public class MyClass { public static void Main() { MyClassMC myMC = new MyClassMC(); int j = myMC[1]; // CS0021 } }  
```
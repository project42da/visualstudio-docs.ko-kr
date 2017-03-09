---
title: "컴파일러 경고(수준 1) CS0688 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0688"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0688"
ms.assetid: 8ce5af36-663e-46e8-87e9-bb32555796ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS0688
링크 요청이 있는 'method1'에서 링크 요청이 없는 'method2'를 재정의하거나 구현합니다. 보안 허점이 있을 수 있습니다.  
  
 기본 클래스 메서드를 호출하여 파생 클래스 메서드에 설정된 링크 요청을 쉽게 우회할 수 있습니다. 보안 허점을 방지하려면 기본 클래스 메서드에서도 링크 요청을 사용해야 합니다. 자세한 내용은 [지연된 로드 및 LinkDemand](http://msdn.microsoft.com/ko-kr/1ab877f2-70f4-4e0d-8116-943999dfe8f5)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0688을 생성합니다. 기본 클래스를 수정하지 않고 경고를 해결하려면 재정의하는 메서드에서 보안 특성을 제거합니다. 이 작업으로 보안 문제가 해결되지는 않습니다.  
  
```  
// CS0688.cs // compile with: /W:1 using System; using System.Security.Permissions; class Base { //Uncomment the following line to close the security hole //[FileIOPermission(SecurityAction.LinkDemand, All=@"C:\\")] public virtual void DoScaryFileStuff() { } } class Derived: Base { [FileIOPermission(SecurityAction.LinkDemand, All=@"C:\\")] // CS0688 public override void DoScaryFileStuff() { } static void Main() { } }  
```
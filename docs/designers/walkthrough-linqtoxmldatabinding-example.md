---
title: "연습: LinqToXmlDataBinding 예제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aedf42e8-896c-48fa-88df-7f7c9536aa69
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# 연습: LinqToXmlDataBinding 예제
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 LinqToXmlDataBinding 예제에 대해 설명하고 두 가지 기본 소스 파일인 L2DBForm.xaml과 L2DBForm.xaml.cs의 몇 가지 흥미로운 내용을 살펴봅니다.  
  
## 사전 요구 사항  
 이 연습을 읽기 전에 [방법: LinqToXmlDataBinding 빌드 및 실행 예제](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)에서 설명하는 대로 LinqToXmlDataBinding 프로그램을 빌드하고 실행하는 것이 좋습니다.  
  
## 설명  
 LinqToXmlDataBinding 프로그램은 C\# 및 XAML 소스 파일로 구성된 WPF\(Windows Presentation Foundation\) 응용 프로그램입니다.이 프로그램에는 책 목록을 정의하고 사용자가 이러한 항목을 보고, 추가하고, 삭제하고, 편집할 수 있도록 하는 포함된 XML 문서가 들어 있습니다.이 프로그램은 다음 두 가지 기본 소스 파일로 구성되어 있습니다.  
  
-   L2DBForm.xaml에는 기본 창의 UI\(사용자 인터페이스\)에 대한 XAML 선언 코드가 포함되어 있습니다.또한 책 목록에 대한 포함된 XML 문서와 데이터 공급자를 정의하는 창 리소스 섹션도 포함되어 있습니다.  
  
-   L2DBForm.xaml.cs에는 UI와 연결된 초기화 및 이벤트 처리 메서드가 포함되어 있습니다.  
  
 기본 창은 다음 네 가지 세로 UI 섹션으로 나뉩니다.  
  
-   **XML**에서는 포함된 책 목록의 원시 XML 소스가 표시됩니다.  
  
-   **Book List**에서는 책 항목이 표준 텍스트로 표시되고 사용자가 개별 항목을 선택하고 삭제할 수 있습니다.  
  
-   **Edit Selected Book**에서는 사용자가 현재 선택된 책 항목과 연결된 값을 편집할 수 있습니다.  
  
-   **Add New Book**에서는 사용자가 입력한 값에 따라 새 책 항목을 만들 수 있습니다.  
  
## 단원 내용  
  
|항목|설명|  
|--------|--------|  
|[L2DBForm.xaml 원본 코드](../designers/l2dbform-xaml-source-code.md)|L2DBForm.xaml 파일의 XAML 코드에 대한 내용과 설명이 포함되어 있습니다.|  
|[L2DBForm.xaml.cs 소스 코드](../designers/l2dbform-xaml-cs-source-code.md)|L2DBForm.xaml.cs 파일의 C\# 소스 코드에 대한 내용과 설명이 포함되어 있습니다.|  
  
## 참고 항목  
 [LINQ to XML을 사용한 WPF 데이터 바인딩 예제](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [방법: LinqToXmlDataBinding 빌드 및 실행 예제](../designers/how-to-build-and-run-the-linqtoxmldatabinding-example.md)
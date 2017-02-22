---
title: "Assert 클래스 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assert 클래스"
  - "Assert 문"
  - "단위 테스트, Assert 문"
  - "단위 테스트, Assert 클래스"
ms.assetid: da1b7a0d-4f1d-4d50-a07e-7b3ff60053f9
caps.latest.revision: 27
caps.handback.revision: 27
ms.author: "mlearned"
manager: "douge"
---
# Assert 클래스 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

UnitTestingFramework 네임스페이스의 Assert 클래스를 사용하여 특정 기능을 확인할 수 있습니다.  단위 테스트 메서드는 개발 코드의 메서드 코드를 실행합니다. 그러나 Assert 문이 포함되어 있는 경우에만 코드 동작의 정확성에 대해 보고합니다.  
  
## Asserts 종류  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> 네임스페이스는 다음과 같은 여러 종류의 Assert 클래스를 제공합니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>  
  
 테스트 메서드에서 호출할 수 있는 Assert 클래스 메서드\(예: Assert.AreEqual\(\)\)의 수는 제한되어 있지 않습니다.  Assert 클래스에는 선택할 수 있는 많은 메서드가 있고 이러한 메서드 중 많은 메서드가 오버로드를 여러 개 가지고 있습니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>  
  
 CollectionAssert 클래스를 사용하여 개체 컬렉션을 비교하고 하나 이상의 컬렉션의 상태를 확인할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>  
  
 StringAssert 클래스를 사용하여 문자열을 비교합니다.  이 클래스에는 StringAssert.Contains, StringAssert.Matches, StringAssert.StartsWith 등과 같은 여러 유용한 메서드가 포함되어 있습니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>  
  
 AssertFailedException 예외는 테스트가 실패할 때마다 throw됩니다.  제한 시간이 초과되거나, 예상치 못한 예외가 throw되거나, 실패라는 결과를 생성하는 Assert 문이 포함되어 있으면 테스트가 실패합니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>  
  
 AssertInconclusiveException은 테스트에서 결과를 작성할 수 없음이라는 결과가 생성될 때마다 throw됩니다.  일반적으로 아직 작업 중인 테스트에 Assert.Inconclusive 문을 추가하여 테스트를 실행할 준비가 되지 않았음을 나타낼 수 있습니다.  
  
> [!NOTE]
>  또 다른 방법은 실행 준비가 완료되지 않은 테스트를 Ignore 특성으로 표시하는 것입니다.  그러나 이 방법은 사용자가 구현하기 위해 남겨 놓은 테스트의 수에 대한 보고서를 쉽게 생성할 수 없다는 단점이 있습니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>  
  
 새 Assert 예외 클래스를 작성하는 경우 해당 클래스가 기본 클래스 UnitTestAssertException에서 상속하도록 하면 테스트 또는 프로덕션 코드에서 예상치 못한 예외를 throw하지 않고 예외를 어설션 오류로 쉽게 식별할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>  
  
 개발 코드의 메서드에 의해 throw될 것으로 예상되는 예외가 해당 메서드에서 실제로 throw되는지 여부를 테스트 메서드에서 확인하게 하려면 ExpectedExceptionAttribute 특성을 사용하여 테스트 메서드를 데코레이팅합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>   
 [Creating and Running Unit Tests for Existing Code](http://msdn.microsoft.com/ko-kr/e8370b93-085b-41c9-8dec-655bd886f173)
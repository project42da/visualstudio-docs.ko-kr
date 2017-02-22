---
title: "단위 테스트에서 Microsoft.VisualStudio.TestTools.UnitTesting 멤버 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fa335fd-e442-448f-913f-25a19df90a93
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "mlearned"
manager: "douge"
---
# 단위 테스트에서 Microsoft.VisualStudio.TestTools.UnitTesting 멤버 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

단위 테스트 프레임워크는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 단위 테스트를 지원합니다.  단위 테스트를 코딩할 때는 <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework> 네임스페이스의 클래스와 멤버를 사용합니다.  단위 테스트를 처음부터 새로 작성했거나 테스트할 코드에서 생성된 단위 테스트를 구체화하는 경우에 이 항목을 사용할 수 있습니다.  
  
## 요소 그룹  
 단위 테스트 프레임워크에 대한 개요를 더욱 확실하게 설명하기 위해 이 단원에서는 UnitTesting 네임스페이스의 요소를 관련 기능의 그룹으로 구성합니다.  
  
> [!NOTE]
>  이름 끝에 Attribute 문자열이 추가되는 특성 요소를 Attribute 문자열과 함께 또는 이 문자열 없이 사용할 수 있습니다.  예를 들어 다음 두 코드 예제는 동일하게 작동합니다.  
>   
>  `[TestClass()]`  
>   
>  `[TestClassAttribute()]`  
  
### 데이터 기반 테스트를 위해 사용되는 요소  
 데이터 기반 단위 테스트를 설정하는 데 다음 요소를 사용합니다.  자세한 내용은 [방법: 데이터 기반 단위 테스트 만들기](../test/how-to-create-a-data-driven-unit-test.md) 및 [연습: 구성 파일을 통한 데이터 소스 정의](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)를 참조하십시오.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataAccessMethod>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElement>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DataSourceElementCollection>  
  
## 호출 순서를 설정하는 데 사용되는 특성  
 다음 특성 중 하나로 데코레이팅된 코드 요소는 지정할 때 호출됩니다.  자세한 내용은 [Anatomy of a Unit Test](http://msdn.microsoft.com/ko-kr/a03d1ee7-9999-4e7c-85df-7d9073976144)을 참조하십시오.  
  
### 어셈블리의 경우  
 어셈블리가 로드된 직후와 어셈블리가 언로드되기 직전에 AssemblyInitialize와 AssemblyCleanup이 호출됩니다.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyInitializeAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssemblyCleanupAttribute>  
  
### 클래스의 경우  
 클래스가 로드된 직후와 클래스가 언로드되기 직전에 ClassInitialize와 ClassCleanup이 호출됩니다.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassInitializeAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ClassCleanupAttribute>  
  
### 테스트 메서드의 경우  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestInitializeAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestCleanupAttribute>  
  
## 테스트 클래스와 메서드를 식별하는 데 사용되는 특성  
 모든 테스트 클래스에는 TestClass 특성이 있어야 하며 모든 테스트 메서드에는 TestMethod 특성이 있어야 합니다.  자세한 내용은 [Anatomy of a Unit Test](http://msdn.microsoft.com/ko-kr/a03d1ee7-9999-4e7c-85df-7d9073976144)을 참조하십시오.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestClassAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestMethodAttribute>  
  
## Assert 클래스 및 관련 예외  
 단위 테스트에서는 여러 종류의 Assert 문, 예외 및 특성을 사용하여 특정 응용 프로그램 동작을 확인할 수 있습니다.  자세한 내용은 [Assert 클래스 사용](../test/using-the-assert-classes.md)을 참조하십시오.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.Assert>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CollectionAssert>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.StringAssert>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertFailedException>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.AssertInconclusiveException>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.UnitTestAssertException>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.ExpectedExceptionAttribute>  
  
## TestContext 클래스  
 특정 테스트 메서드의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 속성 창에는 다음 특성과 할당된 값이 표시됩니다.  이러한 특성은 단위 테스트 코드를 통해 액세스되는 특성이 아닙니다.  대신 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE 또는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 테스트 엔진을 통해 단위 테스트가 사용되거나 실행되는 방식에 영향을 미칩니다. 예를 들어 이러한 특성 중 일부는 테스트 관리자 창과 테스트 결과 창에 열로 표시되므로, 테스트와 테스트 결과를 그룹화하고 정렬하는 데 사용할 수 있습니다.  그러한 특성 중 하나는 임의의 메타데이터를 단위 테스트에 추가할 때 사용하는 TestPropertyAttribute입니다.  예를 들어 이 특성을 사용하면 `[TestProperty("TestPass", "Accessibility")]`로 단위 테스트를 표시하여 이 테스트에서 다루는 테스트 과정의 이름을 저장할 수 있습니다.  또는 `[TestProperty("TestKind", "Localization")]`과 같이 테스트 종류에 대한 표시기를 저장하는 데 사용할 수도 있습니다.  이 특성을 사용하여 만드는 속성과 할당하는 속성 값은 모두 **테스트 특정** 머리글 아래의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 속성 창에 표시됩니다.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.OwnerAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DeploymentItemAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.DescriptionAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.HostTypeAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.IgnoreAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PriorityAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestPropertyAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.WorkItemAttribute>  
  
## 테스트 구성 클래스  
  
-   <xref:Microsoft.TeamFoundation.TestManagement.Client.ObjectTypes>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.TestConfigurationSection>  
  
## 보고서 생성에 사용되는 특성  
 이 단원에서 설명하는 특성은 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] 팀 프로젝트의 프로젝트 계층 구조 엔터티에 데코레이팅되는 테스트 메서드에 관한 것입니다.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssIterationAttribute>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.CssProjectStructureAttribute>  
  
## 전용 접근자와 함께 사용되는 클래스  
 [Using Publicize to Create a Private Accessor](http://msdn.microsoft.com/ko-kr/2056c6a7-6672-42a7-8f53-fead33c56deb)에 설명된 바와 같이 전용 메서드에 대한 단위 테스트를 생성할 수 있습니다.  이 생성 과정에서는 PrivateObject 클래스의 개체를 인스턴스화하는 전용 접근자 클래스가 만들어집니다.  PrivateObject 클래스는 리플렉션을 전용 접근자 프로세스의 일부로 사용하는 래퍼 클래스입니다.  PrivateType 클래스는 비슷하지만, 전용 인스턴스 메서드 호출 대신 전용 정적 메서드 호출에 사용됩니다.  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateObject>  
  
-   <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework.PrivateType>  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestPlatform.UnitTestFramework>
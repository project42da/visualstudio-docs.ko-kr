---
title: "구현 전략 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSPackage, 구현 전략"
ms.assetid: f5512d4e-666d-4934-bd42-9718fd7e4c06
caps.latest.revision: 23
caps.handback.revision: 23
manager: "douge"
---
# 구현 전략
자동화 추가 기능, VSPackage 또는 MEF\(Managed Extensibility Framework\) 구성 요소 부분을 사용하거나 이 세 가지를 조합하여 Visual Studio를 확장할 수 있습니다. 일반적으로 추가 기능은 VSPackage나 MEF 구성 요소 부분보다 개발하기는 더 쉽지만 덜 강력합니다. 추가 기능은 확장성 인터페이스를 호출할 수 있으며 VSPackage 및 MEF 구성 요소 부분은 Visual Studio 자동화 모델에 액세스할 수 있습니다. 여러 가지 다른 접근법을 조합하여 효과적인 솔루션을 만들 수 있습니다.  
  
 VSPackage는 비관리 코드 또는 관리 코드로 작성될 수 있습니다. MPF\(관리 패키지 프레임워크\)를 사용하여 관리 코드로 새 VSPackage를 작성하는 것이 좋습니다. 비관리 코드로 작성할 수 있는 대부분은 관리 코드로 더 쉽고 안전하게 구현될 수 있습니다. 그러나 비관리 코드로 작성된 레거시 응용 프로그램은 Visual Studio에서 계속 실행됩니다.  
  
 간단한 확장을 통해 도구 창을 추가하거나 또는 상태 표시줄이나 출력 창과 같은 Visual Studio UI 요소에 정보를 전송할 수 있습니다. 서버 탐색기와 같은 Visual Studio 계층 구조로 좀 더 복잡한 응용 프로그램을 작성할 수 있습니다. 프로젝트, 편집기 또는 디자이너를 구현하여 보다 강력해질 수 있습니다. 예를 들어 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 자체적으로 언어 서비스로 구현됩니다.  
  
## 관련 단원  
 [Visual Studio SDK 및 자동화](../Topic/Visual%20Studio%20SDK%20and%20Automation.md)  
 Visual Studio 확장성 응용 프로그램을 만들기 위하여 자동화, VSPackage 또는 조합을 사용하는 방법에 대해 설명합니다.  
  
 [Visual Studio SDK 및 관리 코드](../misc/visual-studio-sdk-and-managed-code.md)  
 관리 코드로 VSPackage를 작성하는 여러 가지 방법을 비교합니다.  
  
 [Visual Studio IDE 개념](../misc/visual-studio-ide-concepts.md)  
 VSPackage 및 서비스 이용 방법의 기본 사항을 설명합니다.  
  
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)  
 상태 및 출력 창과 같이 Visual Studio에서 일반적인 UI 응용 프로그램 요소를 설명합니다.  
  
 [Visual Studio에서 계층 구조](../extensibility/internals/hierarchies-in-visual-studio.md)  
 IDE\(통합 개발 환경\)에서 노드 트리로 표시되는 Visual Studio 계층 구조의 개요를 제공합니다.  
  
 [프로젝트](../extensibility/internals/projects.md)  
 프로젝트 및 솔루션 클래스의 개요를 제공합니다.  
  
 [편집기와 언어 서비스 확장](../extensibility/editor-and-language-service-extensions.md)  
 코드 및 텍스트 편집기를 확장하는 방법과 사용자 지정 편집기 및 디자이너를 만드는 방법을 보여 줍니다.  
  
 [레거시 언어 서비스 확장](../extensibility/internals/legacy-language-service-extensibility.md)  
 언어 서비스를 만드는 방법을 보여 줍니다.  
  
 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)  
 VSSDK에 대한 참조 문서입니다.  
  
## 참고 항목  
 [Visual Studio 확장 프로그램을 개발 하기 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)
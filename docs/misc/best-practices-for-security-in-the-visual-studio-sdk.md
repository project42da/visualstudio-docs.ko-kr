---
title: "Visual Studio SDK의 보안을 위한 모범 사례 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "보안[Visual Studio SDK]"
  - "사용자 계정 컨트롤[Visual Studio SDK]"
  - "Visual Studio SDK, 보안"
  - "UAC(사용자 계정 컨트롤)[Visual Studio SDK]"
  - "보안 모범 사례, Visual Studio SDK"
  - "Windows Vista, 사용자 계정 컨트롤[Visual Studio SDK]"
ms.assetid: 56c8a113-0c53-4969-a009-a2ab58d855c3
caps.latest.revision: 30
caps.handback.revision: 30
manager: "douge"
---
# Visual Studio SDK의 보안을 위한 모범 사례
최고의 제품을 만들기 위해서는 VSPackage 확장에 대한 보안을 이해해야 합니다.  
  
 보안 제품을 사용하면 다음을 보호할 수 있습니다.  
  
-   고객 정보의 기밀성, 무결성 및 가용성  
  
-   시스템 소유자 또는 관리자 제어 아래에 있는 처리 리소스의 무결성 및 가용성  
  
## 보안 취약성  
 보안 취약성은 제품이 올바르게 사용되어도 공격자의 악의적인 작업을 방지할 수 없는 제품의 취약점입니다. 다음은 몇 가지 예입니다.  
  
-   컴퓨터에 대해 사용자보다 높은 권한 얻기  
  
-   사용자 컴퓨터의 작업 가로채기  
  
-   사용자 컴퓨터의 데이터 손상  
  
> [!IMPORTANT]
>  응용 프로그램은 특정 환경에서만 실행되는 것이 아닙니다. 특히 응용 프로그램이 널리 사용되는 경우 예기치 못한 설정에서 응용 프로그램이 사용될 수 있습니다. 코드가 유해한 환경에서 실행되고, 디자인, 작성 및 테스트된다고 가정합니다.  
  
 보안을 강화하여 디자인 및 빌드된 제품 및 시스템은 그렇지 않은 제품보다 더 강력합니다. 보안 제품은 미디어 비평에도 더 면역력이 있고 사용자의 선호도도 높으며 지원 및 업그레이드 비용도 저렴합니다.  
  
## 위험한 API  
 일부 함수는 사용 금지 시 보안 코드가 생성되지 않아 올바르게 사용되지 않을 경우 호출할 때 원치 않는 보안 취약성이 발생할 수 있습니다. 그러나 일부 소프트웨어 프로젝트에서는 여러 가지 보안 개발 방법 중 하나로 안전하게 사용하기 어려운 함수를 금지함으로써 보안 면에서 많은 도움을 얻었습니다. 자세한 내용은 Michael Howard와 David LeBlanc가 작성한 Microsoft Press 책, "Writing Secure Code" 부록 A를 참조하세요.  
  
 대부분의 보안 문제는 적절한 확인 없이 신뢰를 입력한 결과 발생합니다. 코드에 데이터를 입력할 때 데이터를 추적하고 해당 데이터에 대한 작업의 의미를 다시 확인합니다. 데이터가 올바른 형식으로 입력되고 신뢰성이 확인된 경우 대부분의 함수를 사용하여 보안 코드를 작성할 수 있습니다.  
  
## UAC\(사용자 계정 컨트롤\) 문제  
 UAC\(사용자 계정 컨트롤\) 기능의 보안 의미를 이해해야 합니다. 이러한 기능은 운영 체제와 응용 프로그램이 악의적인 공격에 노출되는 가능성을 줄입니다.  
  
1.  [!INCLUDE[win7](../debugger/includes/win7_md.md)]의 UAC에 대한 자세한 내용은 [사용자 계정 컨트롤](http://go.microsoft.com/fwlink/?linkid=159927)을 참조하세요.  
  
2.  [!INCLUDE[win8](../debugger/includes/win8_md.md)]의 UAC에 대한 자세한 내용은 [사용자 계정 컨트롤 설정](http://windows.microsoft.com/windows-8/what-are-uac-settings)을 참조하세요.  
  
 UAC가 도입되기 전에 개발자는 일반적으로 필요하지 않은 경우에도 관리자 권한으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 실행했습니다. 불필요한 상위 권한을 요청하지 않는지 확인할 수 있도록 일반 사용자 권한으로 확장을 개발 및 테스트해야 합니다.  
  
 UAC는 배포에도 영향을 줍니다. UAC를 지원하려면 설치 패키지를 올바르게 작성해야 합니다. 패키지를 잘못 작성하면 설치 관리자에서 일반 사용자 권한을 사용하여 관리자 권한이 필요한 작업을 수행하려고 시도하므로 일반적으로 "액세스 거부" 오류가 발생합니다.  
  
## 참고 항목  
 [Vspackage에서 보안 모범 사례](../extensibility/internals/best-practices-for-security-in-vspackages.md)   
 [보안 응용 프로그램을 만들기 위한 리소스](http://msdn.microsoft.com/ko-kr/0ebf5f69-76f2-498a-a2df-83cf3443e132)   
 [주요 보안 개념](../Topic/Key%20Security%20Concepts.md)
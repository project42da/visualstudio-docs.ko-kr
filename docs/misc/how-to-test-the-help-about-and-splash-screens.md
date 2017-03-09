---
title: "방법: 도움말 정보 및 시작 화면 테스트 | Microsoft Docs"
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
  - "정보 대화 상자"
  - "VSPackage, 시작 화면"
  - "VSPackage, 브랜딩"
ms.assetid: 2b959fa4-56d3-44f4-8c2d-9ea2e6fb269d
caps.latest.revision: 10
caps.handback.revision: 10
manager: "douge"
---
# 방법: 도움말 정보 및 시작 화면 테스트
구현 후  **도움말** 및 시작 화면을 지원, 구현에서 테스트할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
### 도움말 대화 상자를 테스트 하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 프롬프트에서 devenv.exe를 실행의 **\/setup** 전환 합니다.  실험 환경에서 실행 하려면 다음과 같이 입력 합니다.  
  
     **devenv \/rootsuffix Exp \/setup**  
  
     **참고** 만 변경 하는 경우이 단계를 반복 해야의  **도움말** 정보 화면입니다.  
  
2.  실행 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 않고 앞에서 설명한 것 처럼 레지스트리 루트에서는 **\/setup** 전환 합니다.  
  
     **devenv \/rootsuffix Exp**  
  
3.  에  **도움말** 메뉴를 클릭  **에 대 한 Microsoft Visual Studio**.  
  
     VSPackage 이름을 표시는  **설치 제품** 목록입니다.  
  
4.  Vspackage를 목록에서 선택 합니다.  
  
     VSPackage 제품 정보에 표시 되는  **제품 세부 사항** 텍스트 상자입니다.  
  
### 시작 화면을 테스트할 수  
  
1.  Devenv.exe를 실행의 **\/setup** 전환 합니다.  실험 환경에서 실행 하려면 다음과 같이 입력 합니다.  
  
     **devenv \/rootsuffix Exp \/setup**  
  
     **참고** 만 시작 화면 정보를 변경 하는 경우이 단계를 반복 해야 합니다.  
  
2.  실행 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 같은 레지스트리 루트를 그대로 했습니다 언급 되지만에 **\/splash** 대신 전환의 **\/setup** 전환.  
  
     **devenv \/rootsuffix Exp \/splash**  
  
     VSPackage 제품 정보와 로고 시작 화면에 나타납니다.  
  
## 참고 항목  
 [VSPackage 브랜딩](../misc/vspackage-branding.md)
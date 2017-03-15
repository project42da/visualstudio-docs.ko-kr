---
title: "방법: 여러 플랫폼을 대상으로 한 프로젝트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "플랫폼, 대상 플랫폼 변경"
  - "프로젝트[Visual Studio], 플랫폼 대상"
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 방법: 여러 플랫폼을 대상으로 한 프로젝트 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 솔루션에서 여러 CPU 아키텍처 또는 플랫폼을 대상으로 하는 솔루션을 한 번에 구성하는 방법을 제공합니다.  이 속성을 설정할 수 있는 속성 통해 액세스 되는  **구성 관리자** 대화 상자.  
  
## 대상 플랫폼 지정  
 **구성 관리자** 대화 상자를 사용하여 솔루션 수준 및 프로젝트 수준의 구성과 플랫폼을 만들고 설정할 수 있습니다.  솔루션 수준 구성 및 대상의 각 조합에는 고유한 속성 집합이 연결되어 있으므로, 예를 들어 [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] 플랫폼을 대상으로 하는 릴리스 구성, x86 플랫폼을 대상으로 하는 릴리스 구성 및 x86 플랫폼을 대상으로 하는 디버그 구성 간에 쉽게 전환할 수 있습니다.  
  
#### 다른 플랫폼을 대상으로 하도록 구성을 설정하려면  
  
1.  **빌드** 메뉴에서 **구성 관리자**를 클릭합니다.  
  
2.  **활성 솔루션 플랫폼** 상자에서 솔루션의 대상 플랫폼을 선택하거나 **\<새로 만들기\>**를 선택하여 새 플랫폼을 만듭니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]응용 프로그램에서 활성 플랫폼으로 설정 된 플랫폼을 대상으로 컴파일되지는  **구성 관리자** 대화 상자.  
  
## 플랫폼 제거  
 필요 없는 플랫폼은 구성 관리자 대화 상자를 사용하여 제거할 수 있습니다.  이렇게 하면 해당 구성 및 대상 조합에 대해 구성한 모든 솔루션과 프로젝트 설정이 제거됩니다.  
  
#### 플랫폼을 제거하려면  
  
1.  **빌드** 메뉴에서 **구성 관리자**를 클릭합니다.  
  
2.  **활성 솔루션 플랫폼** 상자에서 **\<편집\>**을 선택합니다.  **솔루션 플랫폼 편집** 대화 상자가 나타납니다.  
  
3.  제거할 플랫폼을 클릭한 다음 **제거**를 클릭합니다.  
  
## 한 솔루션의 대상으로 여러 플랫폼 지정  
 구성 및 플랫폼 설정의 조합에 따라 설정을 변경할 수 있으므로 두 개 이상의 플랫폼을 대상으로 할 수 있는 솔루션을 설정할 수 있습니다.  
  
#### 여러 플랫폼을 대상으로 지정하려면  
  
1.  **구성 관리자**를 사용하여 솔루션에 대해 대상 플랫폼을 적어도 두 개 이상 추가합니다.  
  
2.  **활성 솔루션 플랫폼** 목록에서 대상 플랫폼을 선택합니다.  
  
3.  솔루션을 빌드합니다.  
  
#### 여러 솔루션 구성을 한 번에 빌드하려면  
  
1.  **구성 관리자**를 사용하여 솔루션에 대해 대상 플랫폼을 적어도 두 개 이상 추가합니다.  
  
2.  **일괄 빌드** 창을 사용하여 몇 개의 솔루션 구성을 한 번에 빌드합니다.  
  
 예를 들어 솔루션 수준 플랫폼을 [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)]로 설정하고 해당 솔루션 내에 동일 플랫폼을 대상으로 하는 프로젝트가 없도록 할 수 있습니다.  또한 각각 다른 플랫폼을 대상으로 하는 여러 프로젝트를 솔루션에 포함할 수 있습니다.  이러한 상황 중 하나에 해당하는 경우 혼동을 피하기 위해 서술적인 이름의 새 구성을 만드는 것이 좋습니다.  
  
## 참고 항목  
 [방법: 구성 만들기 및 편집](../ide/how-to-create-and-edit-configurations.md)   
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
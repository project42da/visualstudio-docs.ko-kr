---
title: "가상 메모리 부족 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aec803b1-9d76-46bb-8f14-8c63d80112a5
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 가상 메모리 부족
이 메시지는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서 멈추거나 가상 메모리가 부족한 경우에 나타납니다.  그러나 시스템에 가상 메모리가 부족 할 때 오류가 발생하는 것이 아니라 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 주소 공간이 부족 할 때 이 오류가 발생합니다.  대개 이 오류는 Visual Studio의 주소 공간이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 2GB로 제한되는 32비트 운영 체제의 컴퓨터에서 발생합니다.  응용 프로그램이 32 비트 프로세스를 사용하여 작업 하는 경우 4GB의 메모리를 해결할 수 있습니다\(2 ^32 비트\).  그러나 32비트 버전의 Windows에서는 내부 목적\(예를 들어, 컴퓨터의 그래픽 카드 또는 시스템 드라이버 다른 작업\)으로 프로세스 가상 주소 공간을 2GB로 예약합니다.  따라서 32 비트 프로세스의 내부용으로 2GB만 사용할 수 있습니다.  3GB 스위치가 Windows 자체적으로 1GB만 예약하고 프로세스에 3GB 제공 되도록 설정할 수 있습니다.  대부분의 경우에서 성능은 Windows 용에서 1GB의 제한으로 줄어들지 않습니다.  
  
 64 비트 버전의 Windows를 실행하는 시스템에서 프로세스 모두 4GB의 주소 공간을 사용하고 Windows 작업 드라이버는 하드웨어 및 시스템에 대한 64 비트 메모리 주소를 사용할 수 있기 때문에 거의 이 오류가 발생합니다.  그러나 메모리 사용률은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 일부 데이터 집합을 처리할 때 3GB 나 4GB도를 초과할 수 있습니다.  자세한 내용은 다음을 참조하십시오. [Visual Studio: 64비트 버전이 없는 이유는 무엇입니까? \(아직\)](http://go.microsoft.com/fwlink/?LinkId=246307).  
  
 이 오류는 일반적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서 많은 양의 데이터가 캐시되고 있거나 또한 메모리를 많이 소비하는 프로세스가 여러 개 실행 중인 경우에 발생합니다.  
  
 다음과 같은 경우에 많은 양의 데이터가 캐시되지만 대개는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작하기만 하면 문제를 해결할 수 있습니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 설치한 후 처음으로 실행하는 경우  
  
-   확장을 설치하거나 제거하는 경우  
  
-   도구 상자 항목을 **Toolbox** 에서선택하거나 사용자 지정하는 경우  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 변경.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 열려 있는 상태에서 시스템이 절전\(최대 절전\) 모드로 전환되도록 허용하는 경우  
  
 다음과 같은 경우에는 많은 양의 활성 메모리가 필요합니다.  이러한 경우에는 필수 구성 요소만 연 상태로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 실행하거나 추가 프로세스를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 두 번째 인스턴스에서 실행하는 것을 추천합니다.  
  
-   대규모 솔루션을 빌드하는 경우  
  
-   큰 XML 문서 작업  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 이전 버전에서 솔루션 업그레이드  
  
-   솔루션의 대상을 변경하는 경우  
  
-   코드를 편집하는 동안 [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] 실행  
  
-   여러 프로젝트에서 IntelliTrace를 실행하는 경우  
  
 이러한 방법이 오류를 방지하지 않은 경우 [!INCLUDE[win7](../debugger/includes/win7_md.md)] 이상의 시스템에서 다음 구문으로 bcedit.exe를 실행하여 사용 가능한 주소 공간을 늘릴 수 있습니다.  
  
 **bcdedit \/set IncreaseUserVa 3072**  
  
 이 명령이 x86 기반 시스템에서 사용자 모드 가상 메모리 할당을 2GB에서 3GB로 늘려 줍니다.  3GB 스위치를 추가한다면 전체 시스템이 더 많은 메모리에 주소 지정하고 각 응용 프로그램은 사용 가능한 메모리 비율을 더 높일 수 있습니다.  
  
> [!NOTE]
>  Bcdedit.exe 관리자 권한으로 실행 해야 합니다.  시스템에서 BitLocker 암호화가 사용되는 경우에는 Bitlocker를 일시 중지하고 변경 작업을 수행한 후 시스템을 다시 부팅하고 Bitlocker를 다시 사용하도록 설정하십시오.  
  
 3GB로 가상 메모리 할당을 증가한 후에 단일 응용 프로그램의 가상 메모리 중 2GB만 사용할 수 있기 때문에 이 오류가 되풀이 될 수 있습니다.  이 오류가 계속 표시되면 솔루션의 크기를 줄이고 다시 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 시작할 수 있습니다.  리팩터링에 자주 사용되는 프로젝트를 제거 하거나 필요 하지 않은 프로젝트 언로드 솔루션을 줄일 수 있습니다.  솔루션을 빌드할 때 오류가 발생하면 명령 프롬프트에서 빌드 해 보십시오.  
  
## 참고 항목  
 [Resources for Troubleshooting IDE Errors](../ide/reference/resources-for-troubleshooting-integrated-development-environment-errors.md)
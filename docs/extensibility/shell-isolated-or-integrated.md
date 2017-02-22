---
title: "Shell (격리 또는 통합) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio shell"
  - "Visual Studio 셸"
  - "셸 [Visual Studio]"
  - "Visual Studio shell 셸 기반 응용 프로그램"
  - "셸 [Visual Studio] 셸 기반 응용 프로그램"
ms.assetid: c64a9bf0-9bf8-45c3-8fa2-306fa6cab66a
caps.latest.revision: 25
caps.handback.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
---
# Shell (격리 또는 통합)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

통합 또는 격리 모드에서 Visual Studio 기반 응용 프로그램을 만들 수 있습니다. 통합된 모드에서 많은 Visual Studio 기능은 응용 프로그램 외에도 사용할 수 있습니다. 격리 모드에서 사용자 고유의 확장와 함께 배포 하고자 하는 Visual Studio 기능의 하위 집합을 선택 합니다.  
  
## 통합된 모드  
 통합된 모드에는 사용자를가 사용자 지정 도구와 함께 표준 Visual Studio 기능을 사용할 수 있습니다. Integrated shell 주로 프로그래밍 언어 및 소프트웨어 개발 도구를 호스트 하기 위한 것입니다.  
  
 자동으로 통합 된 셸에 빌드된 사용자 지정 도구는 동일한 컴퓨터에 설치 된 Visual Studio의 다른 버전으로 병합 합니다. Visual Studio 설치 되어 있지 않은 경우 통합 Visual Studio shell의 재배포 가능 버전을 제공할 수 있습니다.  
  
 재배포 가능 버전 통합 하는 Visual Studio shell의 프로그래밍 언어와 해당 프로젝트 시스템을 지 원하는 기능을 포함 하지 않습니다.  
  
> [!NOTE]
>  Visual Studio 셸 통합된 모드의 Visual Studio Express 버전을 제외한 모든 버전을 함께 설치할 수 있습니다.  
  
 자세한 내용은 [Visual Studio Shell \(통합\)](../extensibility/visual-studio-shell-integrated.md)을 참조하세요.  
  
## 격리 모드  
 격리 모드를 사용 하면\-나란히 실행 하는 사용자 지정 도구를 만드는 다른 버전의 Visual Studio입니다. 모든 표준 Visual Studio 기능에 따라 사용 하지 않는 Visual Studio 서비스에 액세스할 수 있는 도구에 주로 쓰입니다. Visual Studio isolated shell 기반 응용 프로그램의 모양을 사용자 지정할 수 있습니다. 쉽게 기능 및 응용 프로그램과 함께 표시 하지 않을 메뉴 명령 그룹 해제할 수 있습니다.  
  
 자세한 내용은 [Visual Studio Shell 격리](../extensibility/visual-studio-isolated-shell.md)을 참조하세요.  
  
## 통합 또는 격리 된 셸 응용 프로그램 배포  
 통합 또는 격리 된 셸 응용 프로그램으로 배포 하기 위해 응용 프로그램, 재배포 가능 패키지, 특별 한 통합 또는 격리 된 셸 및 설치 프로그램을 포함 해야 합니다. 배포 및 설치 하는 방법에 대 한 자세한 내용은 참조 [격리 된 셸 응용 프로그램 배포](../extensibility/distributing-isolated-shell-applications.md)합니다.  
  
> [!IMPORTANT]
>  [최종 사용자 사용권 계약 \(EULA\)](https://www.visualstudio.com/en-us/support/legal/mt171552) Visual Studio와 통합 하 고 격리 된 셸이 섹션 데이터 컬렉션을 포함 하는 \(**섹션 3. Data**\).  두 통합 또는 격리 된 셸 소프트웨어 응용 프로그램에 작성 하는 사용자의 Microsoft에서 수집 해야 하는 고객 사용 데이터를 설명 합니다. 자세한 내용은 참조 [Microsoft Visual Studio 제품군 개인 정보 취급 방침](https://www.visualstudio.com/en-us/dn948229)합니다.  
>   
>  고객의 응용 프로그램을 통해 별도 사용 현황 데이터를 수집 하는 경우에 수집 하는 사항의 응용 프로그램의 사용자에 게 적절 한 공지를 제공 해야 합니다. Visual Studio 소프트웨어 개발 키트 라이선스에 따라 응용 프로그램의 일부로 통합 하거나 격리 된 셸 소프트웨어를 배포 하는 경우 다음 중 하나를 포함 해야 합니다.  
>   
>  -   응용 프로그램 라이선스의 일환으로 최종 사용자 사용권 계약  
> -   또는 고객이 Visual Studio를 보호 하는 조건에 동의 하도록 요구 하는 사용자 고유의 EULA 통합 셸 만큼 셸 소프트웨어에 대 한 Microsoft 최종 사용자 사용 조건으로 격리  
  
## 추가 리소스  
 재배포 가능 패키지에 대 한 자세한 내용은 참조는 [Visual Studio 확장성 다운로드](http://go.microsoft.com/fwlink/?LinkID=119298) 웹 사이트입니다.  
  
## 참고 항목  
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)
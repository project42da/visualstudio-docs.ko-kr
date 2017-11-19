---
redirect_url: shell/shell-isolated-or-integrated
title: "Shell (격리 또는 통합) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell
- Visual Studio, Shell
- Shell [Visual Studio]
- Visual Studio shell, shell-based applications
- Shell [Visual Studio], shell-based applications
ms.assetid: c64a9bf0-9bf8-45c3-8fa2-306fa6cab66a
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f06af0b884d404b3fd2e8e36cac235c10d254bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="shell-isolated-or-integrated"></a>Shell (격리 또는 통합)
통합 또는 격리 모드에서 Visual Studio 기반 응용 프로그램을 만들 수 있습니다. 통합된 모드의 경우 대부분 Visual Studio 기능을 응용 프로그램 외에도 사용할 수 있습니다. 격리 모드에서 사용자 고유의 확장과 함께 배포 하고자 하는 Visual Studio 기능 하위 집합을 선택 합니다.  
  
## <a name="integrated-mode"></a>통합된 모드  
 통합된 모드에서는 사용자를가 사용자 지정 도구가 함께 표준 Visual Studio 기능을 사용할 수 있습니다. Integrated shell 주로 프로그래밍 언어와 소프트웨어 개발 도구를 호스트 하기 위한 것입니다.  
  
 Integrated shell에서 자동으로 빌드된 사용자 지정 도구는 다른 버전의 동일한 컴퓨터에 설치 된 Visual Studio와 병합 합니다. Visual Studio가 이미 설치 되어 있지 않으면 Visual Studio 통합 셸의 재배포 가능 버전을 제공할 수 있습니다.  
  
 재배포 가능 버전 통합 하는 Visual Studio shell의 프로그래밍 언어와 해당 프로젝트 시스템을 지 원하는 기능을 포함 하지 않습니다.  
  
> [!NOTE]
>  Visual Studio 셸 통합된 모드는 모든 버전의 Express 버전은 제외 하 고 Visual Studio와 함께 설치할 수 있습니다.  
  
 자세한 내용은 참조 [Visual Studio Shell (통합)](../extensibility/visual-studio-shell-integrated.md)합니다.  
  
## <a name="isolated-mode"></a>격리 모드  
 격리 모드-나란히 실행 하는 사용자 지정 도구를 만들 수 있습니다. Visual Studio의 다른 버전과 함께 합니다. 모든 표준 Visual Studio 기능에 따라 하지 않고 Visual Studio 서비스에 액세스할 수 있는 도구에 대 한 주로 두는 것이 됩니다. Visual Studio 격리 셸 기반 응용 프로그램의 모양을 사용자 지정할 수 있습니다. 쉽게 기능 및 해당 응용 프로그램과 함께 표시 하지 않을 메뉴 명령 그룹 해제할 수 있습니다.  
  
 자세한 내용은 참조 [Visual Studio 격리 셸](../extensibility/visual-studio-isolated-shell.md)합니다.  
  
## <a name="distributing-your-integrated-or-isolated-shell-application"></a>통합 또는 격리 셸 응용 프로그램 배포  
 통합 또는 격리 셸 응용 프로그램을 배포 하기 위해 응용 프로그램는 특별 한 통합 또는 isolated shell 재배포 가능 패키지, 및 설치 프로그램을 포함 해야 합니다. 배포 및 설치 하는 방법에 대 한 자세한 내용은 참조 [격리 셸 응용 프로그램 배포](../extensibility/distributing-isolated-shell-applications.md)합니다.  
  
> [!IMPORTANT]
>  [EULA 최종 사용자 사용권 계약 ()](https://www.visualstudio.com/en-us/support/legal/mt171552) 셸 데이터 수집에 섹션이 포함 되어 Visual Studio 통합 및 격리에 대 한 (**섹션 3입니다. 데이터**).  소프트웨어 사용자가 어느 통합 또는 격리 셸 응용 프로그램에 구축 하는 Microsoft에서 수집 될 수 있는 고객 사용 현황 데이터를 설명 합니다. 자세한 내용은 참조 [Microsoft Visual Studio 제품 제품군 개인정보취급방침](https://www.visualstudio.com/en-us/dn948229)합니다.  
>   
>  응용 프로그램을 통해 고객의 별도 사용 현황 데이터를 수집 하는 경우 수집 하의 응용 프로그램의 사용자에 게 적절 한 공지를 제공 해야 합니다.  Visual Studio 소프트웨어 개발 키트 라이선스에 따라 응용 프로그램의 일부로 격리 또는 통합 셸 소프트웨어를 배포 하는 경우 다음 중 하나를 포함 해야 합니다.  
>   
>  -   응용 프로그램 라이선스의 일환으로 최종 사용자 사용권 계약  
> -   Visual Studio를 보호 하는 조건에 동의 하도록 고객을 필요로 하는 사용자 고유의 EULA 통합 또는 그 이상의 shell 셸 소프트웨어에 대 한 Microsoft 최종 사용자 사용 조건으로 격리  
  
## <a name="additional-resources"></a>추가 리소스  
 재배포 가능 패키지에 대 한 자세한 내용은 참조는 [Visual Studio 확장성 다운로드](http://go.microsoft.com/fwlink/?LinkID=119298) 웹 사이트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 확장 전달](../extensibility/shipping-visual-studio-extensions.md)
---
redirect_url: shell/distributing-isolated-shell-applications
title: "격리 셸 응용 프로그램 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 250f1d7769f6035e015eeb7247c439b27f913b78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="distributing-isolated-shell-applications"></a>격리 셸 응용 프로그램 배포
격리 셸 응용 프로그램을 만들기 위해 Visual Studio 및 Visual Studio SDK를 설치 해야 합니다. 다른 사용자 또는 고객의 컴퓨터에 응용 프로그램을 배포 하려면 격리 셸에 대 한 특별 한 재배포 가능 패키지를 포함 해야 합니다.  
  
## <a name="prerequisites-for-distributing-isolated-shell-applications"></a>격리 셸 응용 프로그램을 배포 하기 위한 필수 구성 요소  
  
|name|설명|  
|----------|-----------------|  
|Visual Studio SDK|개발 하 고 확장을 테스트할 경우 SDK [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 또한 Visual Studio 격리 셸의 고유한 인스턴스를 만드는 SDK를 사용할 수 있습니다.<br /><br /> Visual Studio는 SDK에 대 한 필수 구성 요소입니다.|  
|Microsoft Visual Studio 격리 셸 재배포 가능 패키지|셸을 격리 재배포 가능한 Visual studio 도구 환경을 구축 하는 경우 설치 프로그램에 포함 해야 합니다. 격리 셸 재배포 가능 패키지는.NET Framework 4.5를 포함합니다.|  
  
## <a name="creating-an-installation-program-for-the-application"></a>응용 프로그램에 대 한 설치 프로그램 만들기  
 통합 또는 격리 셸 응용 프로그램에 대 한 특별 한 설치 프로그램을 만들어야 합니다. 자세한 내용은 참조 [격리 셸 응용 프로그램을 설치](../extensibility/installing-an-isolated-shell-application.md)합니다.  
  
## <a name="allowing-for-updates-to-your-application"></a>응용 프로그램에 대 한 업데이트 허용  
 설치 프로그램을 응용 프로그램 업데이트 않는 Microsoft 업데이트 또는 회사의 업데이트 가능성에 대 한 허용 해야 합니다. 업데이트에 대 한 자세한 내용은 참조 [격리 셸 응용 프로그램에 대 한 지침이 서비스](../extensibility/servicing-guidelines-for-isolated-shell-applications.md)합니다.
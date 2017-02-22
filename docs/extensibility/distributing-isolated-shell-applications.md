---
title: "격리 된 셸 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 격리 된 셸 응용 프로그램 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

격리 된 셸 응용 프로그램을 만들기 위해 Visual Studio 및 Visual Studio SDK를 설치 해야 합니다. 다른 사용자 또는 고객의 컴퓨터에 응용 프로그램을 배포 하려면 격리 된 셸에 대 한 특별 한 재배포 가능 패키지를 포함 해야 합니다.  
  
## 격리 된 셸 응용 프로그램을 배포 하기 위한 필수 구성 요소  
  
|이름|설명|  
|--------|--------|  
|Visual Studio SDK|개발 하 고 확장을 테스트 해야 하는 SDK [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 또한 Visual Studio isolated shell의 고유한 인스턴스를 만드는 SDK를 사용할 수 있습니다.<br /><br /> Visual Studio SDK에 대 한 반드시 필요 합니다.|  
|Microsoft Visual Studio Isolated Shell 재배포 가능 패키지|Visual studio의 도구 환경을 빌드할 때 설치 프로그램에 포함 하는 재배포 가능 격리 셸. Isolated Shell 재배포 가능 패키지는.NET Framework 4.5에 포함 됩니다.|  
  
## 응용 프로그램에 대 한 설치 프로그램 만들기  
 통합 또는 격리 된 셸 응용 프로그램에 대 한 특별 한 설치 프로그램을 만들어야 합니다. 자세한 내용은 [격리 된 셸 응용 프로그램 설치](../extensibility/installing-an-isolated-shell-application.md)을 참조하세요.  
  
## 응용 프로그램에 대 한 업데이트 허용  
 설치 프로그램을 응용 프로그램 업데이트 됩니다, Microsoft 업데이트 또는 회사의 업데이트 가능성에 대 한 허용 해야 합니다. 업데이트에 대 한 자세한 내용은 참조 [격리 된 셸 응용 프로그램에 대 한 지침을 서비스](../extensibility/servicing-guidelines-for-isolated-shell-applications.md)합니다.
---
title: 문서에 신뢰를 부여
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], trust
- inclusion lists [Office development in Visual Studio], about inclusion lists
- trust [Office development in Visual Studio], 2007 Office system
- granting trust [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f95887d5d540fd1acd95b8af1275c4b4054c8764
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="grant-trust-to-documents"></a>문서에 신뢰를 부여
  문서 수준 프로젝트에는 인증서를 사용하여 매니페스트에 서명하거나 신뢰 프롬프트를 클릭하는 것과 같은 응용 프로그램 수준 프로젝트와 같은 보안 요구 사항이 있습니다. 또한 문서 또는 통합 문서는 신뢰할 수 있는 위치로 지정된 디렉터리에 있어야 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="trusted-locations"></a>신뢰할 수 있는 위치  
 응용 프로그램에서 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 Office 2010 사용자가 신뢰할 수 있는 위치와 같은 보안 및 개인 정보 설정을 구성할 수 있는 보안 센터가 있습니다. Office 솔루션에 대 한 로컬 컴퓨터 신뢰할 수 있는 위치로 간주 됩니다. 그러나 더 큰 위험으로 인해 시스템, 각 사용자 및 Internet Explorer에 대한 임시 폴더와 같이 신뢰할 수 없는 특정 디렉터리가 있습니다.  
  
 보안 센터에 대 한 자세한 내용은 참조 [Office 2010의 보안 및 정책 설정과](http://go.microsoft.com/fwlink/?LinkId=89202)합니다. 만들기, 관리, 제거 및 신뢰할 수 있는 폴더를 구성 하는 방법에 대 한 자세한 내용은 참조 [2007 Office system의 신뢰할 수 있는 위치 및 신뢰할 수 있는 게시자 설정 구성](http://go.microsoft.com/fwlink/?LinkId=89203) 및 [만들기, 제거 또는 변경 된 파일을 저장할 위치를 신뢰할 수 있는](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62)합니다.  
  
## <a name="security-considerations-for-office-solutions"></a>Office 솔루션에 대 한 보안 고려 사항  
 신뢰할 수 있는 위치에 추가할 폴더를 고려할 때 몇 가지 보안 고려 사항이 있습니다.  
  
-   로컬 폴더는 더 안전한 것으로 간주하고 암시적으로 신뢰할 수 있습니다. 파일 공유와 같은 원격 위치는 신뢰할 수 있는 위치로 지정해야 합니다.  
  
-   신뢰할 수 있는 위치에 디렉터리를 추가하면 이 작업은 Office 솔루션뿐만 아니라 VBA 및 ActiveX 코드에도 완전 신뢰를 부여합니다. 이러한 이유로 루트 디렉터리 및 *내 문서* 폴더를 지정 해야 신뢰할 수 있는 것입니다.  
  
-   신뢰할 수 있는 위치를 사용하여 문서 자체를 신뢰할 수 있지만 사용자 지정을 신뢰하려면 추가 권한이 필요합니다. 인증서로 매니페스트에 서명, 신뢰 프롬프트를 클릭 하거나 Office 솔루션에 설치를 사용 하 여 사용자 지정에 완전 신뢰를 부여할 수는 *Program Files* 디렉터리입니다.  
  
-   문서 수준 솔루션의 문서 또는 통합 문서는 어셈블리와 같은 디렉터리나 다른 디렉터리에 저장할 수 있습니다. 예를 들어 문서는 SharePoint 서버에 있고 어셈블리는 네트워크 파일 공유에 있을 수 있습니다. 자세한 내용은 참조 [하는 방법: ClickOnce를 사용 하 여 SharePoint 서버에 문서 수준의 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션에 신뢰를 부여](../vsto/granting-trust-to-office-solutions.md)   
 [Office 솔루션 보안 문제 해결](../vsto/troubleshooting-office-solution-security.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  
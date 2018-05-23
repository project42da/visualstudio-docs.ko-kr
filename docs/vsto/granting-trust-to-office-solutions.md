---
title: Office 솔루션에 신뢰를 부여
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
ms.openlocfilehash: cfce58ca765e7e3710ecb55a1c84c09f0ee14f52
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="grant-trust-to-office-solutions"></a>Office 솔루션에 신뢰를 부여
  Office 솔루션으로 각 대상 컴퓨터의 보안 정책을 수정 솔루션 어셈블리, 응용 프로그램 매니페스트, 배포 매니페스트 및 문서를 신뢰할 신뢰를 부여 합니다. 또는 최종 사용자 하 여 Office 솔루션에 신뢰를 부여할 수 있습니다.  
  
 응용 프로그램 및 배포 매니페스트에 서명 하 여 Office 솔루션에 완전 신뢰를 부여할 수 있습니다.  
  
 최종 사용자의 신뢰 여부를 결정 하 여 Office 솔루션에 신뢰를 부여할 수는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트입니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="Signing"></a> 응용 프로그램 및 배포 매니페스트에 서명 하 여 솔루션을 신뢰 합니다.  
 모든 응용 프로그램 및 배포 매니페스트 Office 솔루션을 게시자를 식별 하는 인증서로 서명 해야 합니다. 인증서 신뢰를 결정 하기 위한 기초를 제공 합니다.  
  
 임시 인증서를 만들고는 솔루션을 디버깅 하는 동안 실행 되므로 빌드 시간에 신뢰를 부여 합니다. 임시 인증서로 서명 하는 솔루션을 게시 하는 경우에 최종 사용자는 신뢰 결정을 내리는 나타납니다.  
  
 신뢰할 수 없는 인증서를 사용 하 여 솔루션을 등록 하는 경우 솔루션 신뢰 결정을 내리는 데 최종 사용자에 게 확인 하지 않고 자동으로 설치 됩니다. 참조 서명용 인증서를 얻는 방법에 대 한 자세한 내용은 [ClickOnce 및 Authenticode](/visualstudio/deployment/clickonce-and-authenticode)합니다. 인증서를 얻은 후 인증서를 신뢰할 수 있는 게시자 목록에 추가 하 여 명시적으로 신뢰할 수 있어야 합니다. 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램에 대 한 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)합니다.  
  
 개발자가 임시 인증서를 사용 하 여 솔루션, 로그인 한 경우 관리자가 다시 서명할 수는 알려져 있고 신뢰할 수 있는 인증서로 사용자 지정 매니페스트 생성 및 편집 도구를 사용 하 여 (*mage.exe*), 중 하나인는 Microsoft.NET Framework 도구입니다. 솔루션을 서명 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 기호 Office 솔루션](../vsto/how-to-sign-office-solutions.md) 및 [하는 방법: 응용 프로그램 및 배포 매니페스트에 서명](/visualstudio/ide/how-to-sign-application-and-deployment-manifests)합니다.  
  
##  <a name="TrustPrompt"></a>ClickOnce 신뢰 프롬프트를 사용 하 여 솔루션 신뢰  
 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 솔루션의 인증서를 신뢰 하는 조직 전체의 정책이 없는 경우 신뢰 결정을 내리는 데 최종 사용자 메시지를 표시 합니다. 최종 사용자는 솔루션에 신뢰를 부여, URL와 공개 키를 저장할 신뢰 결정이 포함 된 포함 목록 항목이 생성 됩니다. 신뢰할 수 있는 사용자 지정을 실행할 때 나중에, 최종 사용자에 게 다시 묻지 않습니다.  
  
 관리자가 사용 하지 않도록 설정할 수는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 또는 Authenticode 인증서로 서명 된 솔루션에 대해서만 발생 하도록 요구 합니다. MyComputer "," LocalIntranet "," Internet "," TrustedSites, "및" UntrustedSites 영역에 대 한 이러한 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: ClickOnce 신뢰 프롬프트 동작 구성](/visualstudio/deployment/how-to-configure-the-clickonce-trust-prompt-behavior)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [문서에 신뢰를 부여](../vsto/granting-trust-to-documents.md)   
 [Office 솔루션 보안 문제 해결](../vsto/troubleshooting-office-solution-security.md)   
 [Office 솔루션에 대 한 특정 보안 고려 사항](../vsto/specific-security-considerations-for-office-solutions.md)  
  
  
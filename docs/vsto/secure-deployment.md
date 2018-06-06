---
title: 안전한 배포
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 47cecda571a6826c2d7e845945c05d0264971134
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693333"
---
# <a name="secure-deployment"></a>안전한 배포
  Office 솔루션을 만들 때 개발 컴퓨터를 실행 하려면 프로젝트에 코드를 허용 하도록 자동 업데이트 됩니다. 그러나 솔루션을 배포할 때 인증서를 사용 하 여 솔루션을 서명 하거나 사용 하 여 신뢰 결정을 기반으로 사용할 증명 정보 제공 해야는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키입니다. 자세한 내용은 참조 [Office 솔루션에 신뢰를 부여](../vsto/granting-trust-to-office-solutions.md)합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 문서 수준 사용자 지정에 대 한 네트워크 위치에 문서를 배포 하는 경우 또한 문서 위치를 더해야 Office 응용 프로그램의 보안 센터에서 신뢰할 수 있는 위치 목록. 최종 사용자 컴퓨터 문서 사용 권한을 설정 하는 방법에 대 한 자세한 내용은 참조 [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)합니다.  
  
## <a name="prevent-office-solutions-from-running-code"></a>Office 솔루션에서 코드 실행 방지  
 관리자는 컴퓨터에서 실행 되지 않도록 모든 Office 솔루션을 방지 하기 위해 레지스트리를 사용할 수 있습니다. 관리 코드 확장이 있는 Office 솔루션을 열면, Office 런타임 검사에 대 한 Visual Studio Tools 항목이 있는지 여부를 이름으로 `Disabled` 컴퓨터에서 다음 레지스트리 키 중 하나에 존재 합니다.  
  
-   **HKEY_CURRENT_USER\Software\Microsoft\VSTO**  
  
-   **이**  
  
 Office 솔루션 코드를 실행 하지 않도록 하려면 만듭니다는 `Disabled` 하나 또는 둘 다 이러한 레지스트리 키의 항목에 대 한 값과 다음 데이터 형식 중 하나를 지정 하 고 `Disabled`:  
  
-   REG_SZ 또는 REG_EXPAND_SZ "0" (0)이 아닌 임의의 문자열으로 설정 되어 있습니다.  
  
-   0 (영)이 아닌 값으로 설정 하는 REG_DWORD 합니다.  
  
 Office 솔루션을 실행할 코드를 사용 하려면 둘 다 설정는 `Disabled` 항목을 0 (영) 하거나 레지스트리 항목을 삭제 합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션을 호스팅하거나 실행 하도록 컴퓨터 준비](http://msdn.microsoft.com/en-us/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  
---
title: "방법: ClickOnce 응용 프로그램에 대 한 보안 영역 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
caps.latest.revision: 
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 86dbdf312c1356c6fb63fcfa32f1dd362b4c7599
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램의 보안 영역 설정
ClickOnce 응용 프로그램에 대한 코드 액세스 보안 권한을 설정할 때에는 **프로젝트 디자이너** 의 **보안**페이지에서 기본 권한 집합으로 시작해야 합니다.  
  
 대부분의 경우, 제한된 권한 집합을 포함하는 **인터넷** 영역 또는 더 큰 권한 집합을 포함하는 **로컬 인트라넷** 영역을 선택할 수 있습니다. 응용 프로그램에 사용자 지정 권한이 필요한 경우 **사용자 지정** 보안 영역을 선택하여 설정할 수 있습니다. 사용자 지정 권한을 설정하는 방법에 대한 자세한 내용은 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)을 참조하세요.  
  
### <a name="to-set-a-security-zone"></a>보안 영역을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **보안** 탭을 클릭합니다.  
  
3.  **ClickOnce 보안 설정 사용** 확인란을 선택합니다.  
  
4.  **부분 신뢰 응용 프로그램** 옵션 단추를 선택합니다.  
  
     **ClickOnce 보안 권한** 섹션의 컨트롤이 사용됩니다.  
  
5.  **설치할 응용 프로그램을 가져올 영역** 드롭다운 목록에서 보안 영역을 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: ClickOnce 응용 프로그램의 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)
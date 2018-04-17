---
title: '방법: ClickOnce 보안 설정 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- security [Visual Studio], ClickOnce applications
- ClickOnce deployment, security settings
- security settings, ClickOnce deployment
ms.assetid: 73cd3e9d-cd72-4ad2-8cae-94d6bb6b01e0
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5c59786a49f09efd2dc4d906511ac2602c765c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-enable-clickonce-security-settings"></a>방법: ClickOnce 보안 설정 사용
응용 프로그램을 게시 하려면 ClickOnce 응용 프로그램에 대 한 코드 액세스 보안을 사용 해야 합니다. 게시 마법사를 사용 하 여 응용 프로그램을 게시할 때 자동으로 수행 됩니다.  
  
 경우에 따라 코드 액세스 보안을 사용 하면 성능에 미치는 영향을 빌드하거나; 응용 프로그램을 디버깅할 때 이러한 경우를 일시적으로 보안 설정을 지정할 수 있습니다.  
  
 ClickOnce 보안 설정 사용 하거나 사용 하지 않도록 설정 수는 **보안** 의 페이지는 **프로젝트 디자이너**합니다.  
  
### <a name="to-enable-clickonce-security-settings"></a>ClickOnce 보안 설정 사용 하도록 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **보안** 탭을 클릭합니다.  
  
3.  **ClickOnce 보안 설정 사용** 확인란을 선택합니다.  
  
     이제 보안 페이지에서 응용 프로그램에 대 한 보안 설정을 지정할 수 있습니다.  
  
    > [!NOTE]
    >  이 확인란으로 응용 프로그램을 게시할 때마다 자동으로 선택 됩니다는 **게시** 마법사.  
  
### <a name="to-disable-clickonce-security-settings"></a>ClickOnce 보안 설정 사용 안 함  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **보안** 탭을 클릭합니다.  
  
3.  지우기는 **ClickOnce 보안 설정 사용** 확인란 합니다.  
  
     응용 프로그램은 완전 신뢰 수준 보안 설정을;으로 실행 됩니다. 에 있는 모든 설정의 **보안** 페이지는 무시 됩니다.  
  
    > [!NOTE]
    >  게시 마법사를 사용 하는 응용 프로그램을 게시할 때마다가 확인란을 선택 합니다. 응용 프로그램이 게시 된 후에 다시 지워야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 보안](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)   
 

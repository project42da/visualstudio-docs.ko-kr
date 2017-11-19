---
title: "방법: ClickOnce 오프 라인 지정 또는 온라인 설치 모드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 5376ef32ce768100af8bc1c9f18267f7ac39895a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>방법: ClickOnce 오프라인 또는 온라인 설치 모드 지정
`Install Mode` 에 대 한 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 않을 것인지를 응용 프로그램이 사용할 수 있는 오프 라인 또는 온라인 결정 합니다. 선택 하는 경우 **응용 프로그램을 온라인만**, 사용자에 액세스할 수 있어야 합니다.는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 위치 (웹 페이지 또는 파일 공유) 응용 프로그램을 실행 하기 위해 게시 합니다. 선택 하는 경우 **응용 프로그램을 오프 라인으로**, 응용 프로그램 항목을 추가 하는 **시작** 메뉴 및 **프로그램 추가 / 제거** 대화 상자, 사용자가 연결 되어 있지 않은 경우 응용 프로그램을 실행할 수 있습니다.  
  
 `Install Mode` 에 설정 될 수는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
 **참고** 는 `Install Mode` 게시 마법사를 사용 하 여 설정할 수도 있습니다. 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>ClickOnce 응용 프로그램에서 사용할 수 있도록 온라인만  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  에 **모드 설치 및 설정을** 영역에서 클릭는 **응용 프로그램을 온라인만** 옵션 단추입니다.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>온라인 또는 오프 라인으로 ClickOnce 응용 프로그램을 사용할 수 있도록 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  에 **모드 설치 및 설정을** 영역에서 클릭는 **응용 프로그램을 오프 라인으로** 옵션 단추입니다.  
  
     항목을 추가 하는 응용 프로그램을 설치 하면는 **시작** 메뉴와 **프로그램 추가 / 제거** 제어판에서.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: ClickOnce 응용 프로그램 게시 마법사를 사용 하 여 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)
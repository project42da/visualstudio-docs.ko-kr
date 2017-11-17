---
title: "방법: ClickOnce 응용 프로그램에 대 한 게시 페이지 지정 | Microsoft Docs"
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
- deploying applications [ClickOnce], specifying publish page
- Publish Page property
- publishing, ClickOnce
- ClickOnce deployment, specifying publish page
ms.assetid: 9d70eebb-bdee-4b42-8e7e-7a07e199bdf7
caps.latest.revision: "18"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: e05718d2a00df76d2c78e16c5b4473ab48d43a39
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-specify-a-publish-page-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램의 게시 페이지 지정
게시 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 기본 웹 페이지 (publish.htm) 생성 되 고 응용 프로그램과 함께 게시 합니다. 이 페이지에서는 설명 하는 도움말 항목에 대 한 링크 및/응용 프로그램 또는 필수 구성 요소를 설치 하기 위한 링크를 사용 하는, 응용 프로그램의 이름을 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]합니다. **게시 페이지** 프로젝트에 대 한 속성에 대 한 웹 페이지에 대 한 이름을 지정할 수 있습니다 프로그램 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
 게시 페이지 지정 되 면를 게시 하면 다음에 복사 됩니다; 게시 위치로 다시 게시 하는 경우 하지 덮어쓰는지 않습니다. 페이지의 모양을 사용자 지정 하려는 경우 변경한 내용이 삭제 될 염려 하지 않고 그렇게 할 수 있습니다. 자세한 내용은 참조 [하는 방법: ClickOnce 기본 웹 페이지 사용자 지정](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)합니다.  
  
 **게시 페이지** 속성을 설정할 수 있습니다는 **게시 옵션** 에서 액세스할 수 있는 대화 상자는 **게시** 의 창 고 **프로젝트 디자이너**.  
  
### <a name="to-specify-a-custom-web-page-for-a-clickonce-application"></a>ClickOnce 응용 프로그램에 대 한 사용자 지정 웹 페이지를 지정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  선택 된 **게시** 창.  
  
3.  클릭는 **옵션** 버튼을 클릭은 **게시 옵션** 대화 상자.  
  
4.  클릭 **배포**합니다.  
  
5.  에 **게시 옵션** 대화 상자에서 다음 사항을 확인는 **게시 한 후 열려 있는 배포 웹 페이지** 확인란을 선택 (선택 해서는 기본적으로).  
  
6.  에 **배포 웹 페이지:** 상자, 웹 페이지에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.  
  
### <a name="to-prevent-the-publish-page-from-launching-each-time-you-publish"></a>게시 페이지 게시 될 때마다 시작 하지 않도록 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  선택 된 **게시** 창.  
  
3.  클릭는 **옵션** 버튼을 클릭은 **게시 옵션** 대화 상자.  
  
4.  클릭 **배포**합니다.  
  
5.  에 **게시 옵션** 대화 상자에서 지우기는 **게시 한 후 열려 있는 배포 웹 페이지** 확인란 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: ClickOnce 응용 프로그램 게시 마법사를 사용 하 여 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [방법: ClickOnce 기본 웹 페이지 사용자 지정](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)
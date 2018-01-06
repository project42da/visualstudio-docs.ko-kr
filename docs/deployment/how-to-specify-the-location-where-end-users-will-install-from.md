---
title: "방법:에서 최종 사용자가 설치 하는 위치를 지정 합니다. | Microsoft Docs"
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
- deploying applications [ClickOnce], specifying an installation URL
- URLs, specifying an installation URL
- installation, specifying installation an URL
- Installation URL property
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: a3a2770933f4a9f600b12a2d601deca855de3a94
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-location-where-end-users-will-install-from"></a>방법: 최종 사용자의 설치 원본 위치 지정
게시 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 다운로드 하 고 응용 프로그램을 설치 하려면 사용자가 이동 하지 일 필요는 처음 응용 프로그램을 게시할 위치입니다. 예를 들어 일부 조직에서는 개발자 응용 프로그램을 스테이징 서버에 게시 될 수로 이동한 다음 관리자는 웹 서버에 응용 프로그램입니다.  
  
 이 경우 사용할 수 있습니다는 `Installation URL` 속성을 통해 사용자가 응용 프로그램 다운로드 이동할 웹 서버를 지정 합니다. 이것이 필요한 응용 프로그램 매니페스트 업데이트를 찾을 수 있는 위치를 알 수 있도록 합니다.  
  
 `Installation URL` 속성에 설정 될 수는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
 **참고** 는 `Installation URL` 를 사용 하 여 속성 설정할 수도 있습니다는 **PublishWizard**합니다. 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-specify-an-installation-url"></a>설치 URL을 지정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  설치 URL 필드에 서식 http://www.microsoft.com/ApplicationName 또는 형식을 사용 하 여 UNC 경로 사용 하 여 정규화 된 URL을 사용 하 여 설치 위치를 입력 \\\Server\ApplicationName 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio의 파일 복사 위치 지정](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
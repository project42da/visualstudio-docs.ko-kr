---
title: "방법: ClickOnce 응용 프로그램에 대 한 기본 웹 페이지를 사용자 지정 | Microsoft Docs"
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
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
caps.latest.revision: "14"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 4927a5909ba4b09e796d52d81cc9821a5a9c4820
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램의 기본 웹 페이지 사용자 지정
ClickOnce 응용 프로그램 웹에 게시, 웹 페이지 자동으로 생성 되 고 응용 프로그램과 함께 게시 합니다. 기본 페이지에는 응용 프로그램 및 응용 프로그램을 설치, 필수 구성 요소를 설치 하거나 MSDN에서 도움말에 액세스 하는 링크의 이름을 포함 합니다.  
  
> [!NOTE]
>  페이지를 보고 하는 컴퓨터와 기능에 따라 달라 페이지에 표시 되는 실제 링크를 포함 하는 필수 구성 요소입니다.  
  
 웹 페이지에 대 한 기본 이름인 Publish.htm; 이름을 변경할 수 있습니다는 **프로젝트 디자이너**합니다. 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램에 대 한 게시 페이지 지정](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)합니다.  
  
 Publish.htm 웹 페이지 보다 최신 버전이 있는 경우에 게시 됩니다.  
  
> [!NOTE]
>  변경한 사용자 **게시** 설정을 Publish.htm 페이지 예외적으로 영향을 주지 것입니다:를 추가 하거나 처음 게시 한 후 필수 구성 요소를 제거 하는 경우 필수 구성 요소 목록은 더 이상 됩니다 정확 하 게 합니다. 변경 내용을 반영 하기 위해 필수 구성 요소 링크에 대 한 텍스트를 편집 해야 합니다.  
  
### <a name="to-customize-the-publish-web-page"></a>게시 웹 페이지 사용자 지정 하려면  
  
1.  웹 위치를 ClickOnce 응용 프로그램을 게시 합니다. 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
2.  웹 서버에서 비주얼 웹 디자이너 또는 다른 HTML 편집기에서 Publish.htm 파일을 엽니다.  
  
3.  필요에 따라 페이지를 사용자 지정 하 고 저장 합니다.  
  
4.  선택 사항입니다. Visual Studio를에서 지정 된 게시 웹 페이지를 덮어쓰지 않도록 하려면 선택을 취소 **자동으로 배포 웹 페이지 생성 모든 게시** 게시 옵션 대화 상자에서 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램의 게시 페이지 지정](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)
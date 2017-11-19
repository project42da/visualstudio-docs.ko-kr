---
title: "방법: ClickOnce 응용 프로그램 필수 구성 요소 설치 | Microsoft Docs"
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
- deploying applications [ClickOnce], prerequisites
- prerequisites, ClickOnce
- components, bootstrapping
ms.assetid: e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 44acef520a15b86e15906eb4197f538b23b92d8a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-install-prerequisites-with-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치
모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 올바른 버전의.NET Framework 실행 되기 전에 컴퓨터에 설치 되어 있는지 필요 있으며 대부분의 응용 프로그램 필수 구성 요소 뿐입니다. 게시 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 응용 프로그램과 함께 패키징되 필수 구성 요소 집합을 선택할 수 있습니다. 설치 시에는 확인을 수행 하는 경우 이미 존재 합니다; 확인 하려면 각 필수 구성 요소에 대 한 설치 하기 전에 설치 됩니다 하지 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
 패키징 필수 구성 요소를 게시 하는 대신 구성 요소에 대 한 다운로드 위치를 지정할 수 있습니다. 예를 들어 게시 하는 모든 응용 프로그램에 필수 구성 요소를 포함 하는 대신 사용할 수 있습니다는 중앙된의 파일 공유 또는 모든 프로그램 필수 구성 요소에 대 한 설치 관리자가 들어 있는 웹 위치-설치 시 구성 요소 다운로드 되 고 해당 위치에서 설치 합니다.  
  
> [!IMPORTANT]
>  첫 번째 게시 하기 전에 개발 컴퓨터에 필수 구성 요소 설치 관리자 패키지를 추가 해야 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 자세한 내용은 참조 [하는 방법: ClickOnce 응용 프로그램에 필수 구성 요소 포함](../deployment/how-to-include-prerequisites-with-a-clickonce-application.md)합니다.  
  
 필수 구성 요소에서 관리 되는 **필수 구성 요소** 에서 액세스할 수 있는 대화 상자는 **게시** 의 창은 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  필수 구성 요소는 미리 결정 된 목록 외에도 사용자 자신의 구성 요소 목록에 추가할 수 있습니다. 자세한 내용은 참조 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)합니다.  
  
### <a name="to-specify-prerequisites-to-install-with-a-clickonce-application"></a>ClickOnce 응용 프로그램으로 설치 하려면 필수 구성 요소를 지정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  선택 된 **게시** 창.  
  
3.  클릭는 **필수 구성 요소** 버튼을 클릭은 **필수 구성 요소** 대화 상자.  
  
4.  **필수 구성 요소** 대화 상자에서 **필수 구성 요소를 설치하기 위한 설치 프로그램 만들기** 확인란이 선택되어 있는지 확인합니다.  
  
5.  에 **필수 구성 요소** 목록에서 구성 요소를 설치 하 고 클릭 하려는 하 **확인**합니다.  
  
     선택한 구성 요소를 패키지 하 고 응용 프로그램과 함께 게시 됩니다.  
  
### <a name="to-specify-a-different-download-location-for-prerequisites"></a>필수 구성 요소에 대 한 다른 다운로드 위치를 지정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  선택 된 **게시** 창.  
  
3.  클릭는 **필수 구성 요소** 버튼을 클릭은 **필수 구성 요소** 대화 상자.  
  
4.  **필수 구성 요소** 대화 상자에서 **필수 구성 요소를 설치하기 위한 설치 프로그램 만들기** 확인란이 선택되어 있는지 확인합니다.  
  
5.  에 **필수 구성 요소에 대 한 설치 위치 지정** 섹션에서 **다음 위치에서 필수 구성 요소 다운로드**합니다.  
  
6.  드롭다운 목록에서 위치를 선택 하거나 URL, 파일 경로 또는 FTP 위치를 입력 한 다음 클릭 **확인 합니다.**  
  
    > [!NOTE]
    >  지정된 된 구성 요소에 대 한 설치 관리자가 지정된 된 위치에 존재 하는지 확인 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
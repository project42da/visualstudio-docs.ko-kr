---
title: '방법: 자동으로 증가 ClickOnce 게시 버전 | Microsoft Docs'
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
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 0a0cc134dbed973681ed43830435a6ce5ae0331c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>방법: ClickOnce 게시 버전 자동 증가
게시 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 변경 하는 응용 프로그램의 `Publish Version` 속성으로 인해 응용 프로그램이 업데이트로 게시 합니다. 기본적으로 Visual Studio 자동 증가 `Revision` 의 숫자는 `Publish Version` 응용 프로그램을 게시할 때마다 합니다.  
  
 이 동작을 비활성화할 수는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>게시 버전 자동 증가 사용 하지 않도록 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  에 **게시 버전** 섹션을 선택 취소는 **자동 수정 번호 각 릴리스마다 증가** 확인란 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: ClickOnce 게시 버전 설정](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
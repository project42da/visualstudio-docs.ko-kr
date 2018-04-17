---
title: '방법: 변경 된 ClickOnce 응용 프로그램에 대 한 게시 언어 | Microsoft Docs'
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
- Publish language property
- ClickOnce deployment, changing publish language
- publishing, ClickOnce
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: f6b1590eb45950cb0e8b9de668b7eabe62d13c3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-publish-language-for-a-clickonce-application"></a>방법: ClickOnce 응용 프로그램의 게시 언어 변경
게시 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 개발 컴퓨터의 culture 및 언어에 대 한 설치 기본값 중 표시 되는 사용자 인터페이스가 있습니다. 지역화 된 응용 프로그램을 게시 하는 경우에 언어와 문화권 지역화 된 버전과 일치 하도록 지정 해야 합니다. 결정 된 `Publish language` 프로젝트에 대 한 속성입니다.  
  
 `Publish language` 속성을 설정할 수는 **게시 옵션** 에서 액세스할 수 있는 대화 상자는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-change-the-publish-language"></a>게시 언어를 변경 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  클릭는 **옵션** 버튼을 클릭은 **게시 옵션** 대화 상자.  
  
4.  클릭 **설명**합니다.  
  
5.  에 **게시 옵션** 대화 상자는 언어를 선택 하 고 문화권에서 **게시 언어** 드롭 다운 목록 및 클릭 **확인**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
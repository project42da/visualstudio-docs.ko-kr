---
title: "방법: CD 설치에 대 한 자동 시작 사용 | Microsoft Docs"
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
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: e3656c3d32dcba946cf66d7fba56a68b3de467f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>방법: CD 설치를 위한 자동 시작 사용
배포 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] CD-ROM 또는 DVD-ROM와 같은 이동식 미디어를 사용 하 여 응용 프로그램을 사용 가능 `AutoStart` 있도록는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 미디어를 삽입할 때 응용 프로그램이 자동으로 시작 합니다.  
  
 `AutoStart`사용할 수는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
### <a name="to-enable-autostart"></a>자동 시작을 사용 하도록 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  클릭는 **옵션** 단추입니다.  
  
     **게시 옵션** 대화 상자가 나타납니다.  
  
4.  클릭 **배포**합니다.  
  
5.  선택 된 **CD 설치는 자동으로 설치를 시작 CD를 삽입 하면** 확인란 합니다.  
  
     응용 프로그램을 게시할 Autorun.inf 파일이 게시 위치에 복사 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
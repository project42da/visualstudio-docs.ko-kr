---
title: '방법: 집합 ClickOnce 게시 버전 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96bb991efed7d5a353fc7b73bcb647190438ff84
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-set-the-clickonce-publish-version"></a>방법: ClickOnce 게시 버전 설정
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` 속성 게시 하려는 응용 프로그램 업데이트로 간주할지 여부를 결정 합니다. 각 시간 버전 번호가 증가, 응용 프로그램이 업데이트로 게시 됩니다.  
  
 `Publish Version` 속성에 설정 될 수는 **게시** 의 페이지는 **프로젝트 디자이너**합니다.  
  
> [!NOTE]
>  자동으로 증가 하는 프로젝트 옵션이 `Publish Version` 속성 될 때마다는 응용 프로그램을 게시할;이 옵션은 기본적으로 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)합니다.  
  
### <a name="to-change-the-publish-version"></a>게시 버전을 변경 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  **게시 버전** 필드, 증가 **주요**, **부**, **빌드**, 또는 **개정** 버전 숫자입니다.  
  
    > [!NOTE]
    >  버전 번호를; 감소 하지 해야 따라서 이렇게 하면 예측할 수 없는 업데이트 동작을 일으킬 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
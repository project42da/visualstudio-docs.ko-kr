---
title: "방법: ClickOnce 게시 버전 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 게시 버전 설정"
  - "게시 버전 속성"
  - "게시, ClickOnce"
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 게시 버전 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] **게시 버전** 속성은 게시할 응용 프로그램을 업데이트로 취급할지 여부를 결정합니다.  버전이 증가할 때마다 응용 프로그램은 업데이트로 게시됩니다.  
  
 **게시 버전** 속성은 **프로젝트 디자이너**의 **게시** 페이지에서 설정할 수 있습니다.  
  
> [!NOTE]
>  응용 프로그램이 게시될 때마다 **게시 버전** 속성을 자동으로 증가시키는 프로젝트 옵션이 있습니다. 이 옵션은 기본적으로 설정되어 있습니다.  자세한 내용은 [방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)를 참조하십시오.  
  
### 게시 버전을 변경하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **게시 버전** 필드에서 **주 버전**, **부 버전**, **빌드** 또는 **수정 버전**을 증가시킵니다.  
  
    > [!NOTE]
    >  버전 번호를 감소시켜서는 안 됩니다. 감소시키는 경우 예상치 못한 업데이트 동작이 발생할 수 있습니다.  
  
## 참고 항목  
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [방법: ClickOnce 게시 버전 자동 증가](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
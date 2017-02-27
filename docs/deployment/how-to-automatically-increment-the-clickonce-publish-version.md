---
title: "방법: ClickOnce 게시 버전 자동 증가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ClickOnce 배포, 게시 버전 자동 증가"
  - "응용 프로그램 배포[ClickOnce], 게시 버전 자동 증가"
  - "게시 버전 속성, 증가"
  - "게시, ClickOnce"
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ClickOnce 게시 버전 자동 증가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시할 때 `Publish Version` 속성을 변경하면 응용 프로그램이 업데이트로 게시됩니다.  기본적으로 Visual Studio에서는 사용자가 응용 프로그램을 게시할 때마다 `Publish Version`의 `Revision`을 증가시킵니다.  
  
 **프로젝트 디자이너**의 **게시** 페이지에서 이 동작을 비활성화할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 게시 버전이 자동으로 증가되지 않게 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **게시 버전** 섹션에서 **릴리스할 때마다 자동으로 수정 번호 증가** 확인란의 선택을 취소합니다.  
  
## 참고 항목  
 [방법: ClickOnce 게시 버전 설정](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
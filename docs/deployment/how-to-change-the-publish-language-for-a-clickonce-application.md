---
title: "방법: ClickOnce 응용 프로그램의 게시 언어 변경 | Microsoft Docs"
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
  - "ClickOnce 배포, 게시 언어 변경"
  - "게시 언어 속성"
  - "게시, ClickOnce"
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램의 게시 언어 변경
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시하는 경우 설치 중에는 기본적으로 개발 컴퓨터의 언어 및 문화권과 일치하는 사용자 인터페이스가 표시됩니다.  지역화된 응용 프로그램을 게시할 경우 지역화된 버전에 맞게 언어 및 문화권을 지정해야 합니다.  이러한 사항은 프로젝트에 대한 `Publish language` 속성에 의해 결정됩니다.  
  
 `Publish language` 속성은 **프로젝트 디자이너**의 **게시** 페이지에서 액세스할 수 있는 **게시 옵션** 대화 상자에서 설정할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 게시 언어를 변경하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **옵션** 단추를 클릭하여 **게시 옵션** 대화 상자를 엽니다.  
  
4.  **설명**을 클릭합니다.  
  
5.  **게시 옵션** 대화 상자의 **게시 언어** 드롭다운 목록에서 언어 및 문화권을 선택한 다음 **확인**을 클릭합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
---
title: "방법: 최종 사용자의 설치 원본 위치 지정 | Microsoft Docs"
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
  - "응용 프로그램 배포[ClickOnce], 설치 URL 지정"
  - "설치 URL 속성"
  - "설치, 설치 URL 지정"
  - "URL, 설치 URL 지정"
ms.assetid: 04a804bf-ed55-4a7a-a1e6-f63ed99c0276
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 최종 사용자의 설치 원본 위치 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시하는 경우 사용자가 응용 프로그램을 다운로드하여 설치하기 위해 이동하는 위치가 반드시 처음에 응용 프로그램을 게시한 위치일 필요는 없습니다.  예를 들어 어떤 조직에서 개발자가 응용 프로그램을 스테이징 서버에 게시하면 관리자는 응용 프로그램을 웹 서버로 옮길 수 있습니다.  
  
 이 경우 `Installation URL` 속성을 사용하여 사용자가 응용 프로그램을 다운로드하기 위해 이동하는 웹 서버를 지정할 수 있습니다.  이를 통해 응용 프로그램 매니페스트는 업데이트를 찾을 위치를 알 수 있게 됩니다.  
  
 `Installation URL` 속성은 **프로젝트 디자이너**의 **게시** 페이지에서 설정할 수 있습니다.  
  
 **참고** `Installation URL` 속성은 **게시 마법사**를 사용하여 설정할 수도 있습니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)를 참조하십시오.  
  
### 설치 URL을 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  설치 URL 필드에 http:\/\/www.microsoft.com\/ApplicationName 형식을 사용하는 정규화된 URL이나 \\\\Server\\ApplicationName 형식을 사용하는 UNC 경로를 사용하여 설치 위치를 입력합니다.  
  
## 참고 항목  
 [방법: Visual Studio의 파일 복사 위치 지정](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
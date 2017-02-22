---
title: "방법: Visual Studio의 파일 복사 위치 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "게시 위치 속성"
  - "게시, 위치 지정"
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: Visual Studio의 파일 복사 위치 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce를 사용하여 응용 프로그램을 게시하는 경우 `Publish Location` 속성에서 응용 프로그램 파일 및 매니페스트가 배치되는 위치를 지정합니다.  이 위치는 파일 경로나 FTP 서버에 대한 경로가 될 수 있습니다.  
  
 `Publish Location` 속성은 **프로젝트 디자이너**의 **게시** 페이지나 게시 마법사를 사용하여 지정할 수 있습니다.  자세한 내용은 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)를 참조하세요.  
  
> [!NOTE]
>  ClickOnce를 사용하여 응용 프로그램 버전을 둘 이상 설치하면 이전 응용 프로그램 버전이 지정한 게시 위치의 Archive 폴더로 이동합니다.  이러한 방식으로 이전 버전이 보관되므로 설치 디렉터리에 이전 버전의 폴더가 남지 않습니다.  
  
### 게시 위치를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **게시** 탭을 클릭합니다.  
  
3.  **게시 위치** 필드에, 다음 형식 중 하나를 사용하여 게시 위치를 입력합니다.  
  
    -   파일 공유나 디스크 경로에 게시하려면 UNC 경로\(\\\\Server\\ApplicationName\)나 파일 경로\(C:\\Deploy\\ApplicationName\)를 사용하여 경로를 입력합니다.  
  
    -   FTP 서버에 게시하려면 ftp:\/\/ftp.microsoft.com\/ApplicationName 형식을 사용하여 경로를 입력합니다.  
  
     찾아보기\(**...**\) 단추가 작동하려면 **게시 위치** 상자에 텍스트가 있어야 합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
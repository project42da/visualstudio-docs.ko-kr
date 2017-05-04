---
title: "방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "배포[Visual Studio에서 SharePoint 개발]"
  - "원격 배포[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 배포"
  - "Visual Studio에서 SharePoint 개발, 원격 배포"
ms.assetid: d9c67fae-d097-4e26-a2b9-0f72ff800987
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 원격 서버에서 SharePoint 솔루션 배포, 게시 및 업그레이드
  로컬 시스템에 SharePoint 솔루션을 배포 하는 것 외에도 SharePoint 솔루션을 샌드박스 로컬 SharePoint 사이트 또는 원격 사이트에 게시할 수 있습니다.  원격 게시 프로세스는 .wsp 파일을 SharePoint 서버에 복사하고, 솔루션을 설치한 다음, 솔루션을 활성화할 수 있도록 해줍니다.  변경한 후에 원격 SharePoint 솔루션 설치를 업그레이드할 수 있습니다.  
  
## 원격 SharePoint 서버에 SharePoint 샌드박스 솔루션을 게시 하려면  
  
1.  **솔루션 탐색기**에서, 게시하려는 샌드박스 프로젝트에 대한 바로 가기 메뉴를 연 후 **게시**를 선택합니다.  
  
2.  **게시** 대화 상자에서 **SharePoint 사이트에 게시** 옵션 버튼을 선택한 다음, https:\/\/mytestsite.sharepoint.microsoftonline.com 와 같이 온라인 게시 사이트에 대한 URL을 입력 합니다.  
  
3.  **게시 후 브라우저에서 솔루션 갤러리 페이지 열기** 옵션 버튼을 선택하여 게시 후 **솔루션 갤러리** 페이지에서 솔루션 목록을 봅니다.  
  
4.  **게시** 버튼을 선택합니다.  
  
5.  사용자 인증이 필요한 경우 원격 서버에 로그온 합니다.  
  
     게시 진행률이 Visual Studio **출력** 창에 표시됩니다.  프로세스가 완료되면 솔루션 \(.wsp\) 파일이 원격 SharePoint 서버에 설치 됩니다.  그러나 이것은 여전히 활성화 해야만 SharePoint에서 사용할 수 있습니다.  
  
6.  **솔루션 갤러리** 페이지에서 SharePoint 응용 프로그램을 선택한 다음, 리본 메뉴에서 **활성화** 버튼을 선택합니다.  
  
7.  **솔루션 정품 인증** 대화 상자의 리본 메뉴에서 **활성화** 버튼을 다시 선택합니다.  
  
     **솔루션 갤러리** 페이지의 **상태** 열은 응용 프로그램 활성화 되어 있음을 나타냅니다.  
  
## 원격 SharePoint 서버의 SharePoint 샌드박스 솔루션 업그레이드하려면  
 SharePoint 샌드박스 솔루션이 이미 원격 서버에 게시된 경우, 다음 프로세스는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 의 응용 프로그램을 변경한 후 업그레이드 하도록 해줍니다.  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 의 SharePoint 패키지 이름을 바꿉니다.  이것을 하려면 **솔루션 탐색기** 에서 package.appxmanifest 파일을 엽니다.  이것은 **패키지 탐색기** 에 표시됩니다.  
  
2.  **패키지 탐색기** 의 **이름** 상자에서 패키지 이름을 고유한 이름으로 변경 합니다.  
  
3.  프로젝트를 저장합니다.  
  
4.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **게시** 를 선택합니다.  
  
5.  **게시** 대화 상자에서 **SharePoint 사이트에 게시** 옵션 버튼을 선택한 다음, 솔루션이 저장 되어 있는 원격 서버에 대한 URL이 없는 경우, 다음을 입력합니다.  
  
6.  **게시 후 브라우저에서 솔루션 갤러리 페이지 열기** 옵션 버튼을 선택하여 게시 후 **솔루션 갤러리** 페이지에서 솔루션 목록을 봅니다.  
  
7.  **게시** 버튼을 선택합니다.  
  
8.  사용자 인증이 필요한 경우 원격 서버에 로그온 합니다.  
  
     최근에 원격 서버에 로그인 한 경우, 인증이 필요할 수도 있습니다.  
  
     이름이 같은 이전 버전의 응용 프로그램이 여전히 SharePoint 서버에 존재 하는 경우, 같은 이름의 패키지가 SharePoint 서버에 이미 존재 한다 라고 알리는 오류가 발생 합니다.  패키지를 게시 하기 전에 이름을 바꾸어야 합니다.  
  
9. SharePoint에서 새 응용 프로그램을 선택한 다음 리본 메뉴에서 **업그레이드** 버튼을 선택합니다.  
  
10. **솔루션 업그레이드** 대화 상자의 리본 메뉴에서 **업그레이드** 버튼을 다시 선택합니다.  **솔루션 갤러리** 페이지의 **상태** 열은 이제 응용 프로그램이 활성화 되어 있음을 나타냅니다.  
  
     이전 버전의 솔루션은 비활성화 되고, 새 버전의 솔루션은 이전 솔루션에서 유지 관리된 데이터와 함께 업그레이드 되고, 새 솔루션이 SharePoint에서 활성화 됩니다.  
  
## 참고 항목  
 [방법: 로컬 SharePoint 사이트에 SharePoint 솔루션 배포 및 게시](../sharepoint/how-to-deploy-and-publish-a-sharepoint-solution-to-a-local-sharepoint-site.md)   
 [SharePoint 솔루션 패키지 만들기](../sharepoint/creating-sharepoint-solution-packages.md)   
 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)   
 [방법: 패키지 디자이너를 사용하여 패키지에 기능과 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)  
  
  
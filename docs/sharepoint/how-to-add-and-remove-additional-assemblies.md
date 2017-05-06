---
title: "방법: 추가 어셈블리 추가 및 제거"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.RAD.CustomAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 패키지"
ms.assetid: d9d1e8db-9df2-4e07-ac8d-59ef05d24090
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: 추가 어셈블리 추가 및 제거
  SharePoint 패키지가 기능을 수행하고 데이터를 얻는 데 다른 어셈블리가 필요한 경우 솔루션 패키지\(.wsp\)에 해당 어셈블리를 추가할 수 있습니다.  이런 방식으로 SharePoint 서버는 패키지와 함께 사용자 지정 어셈블리가 설치되도록 합니다.  
  
 어셈블리와 연결된 안전 컨트롤과 클래스 리소스 파일을 추가하고 변경할 수도 있습니다.  
  
## 추가 어셈블리, 안전 컨트롤 및 클래스 리소스 추가  
 SharePoint 솔루션 패키지에 어셈블리를 추가할 수 있습니다.  샌드박스가 적용된 솔루션의 추가 어셈블리는 전역 어셈블리 캐시로 배포되지만, 샌드박스가 적용된 솔루션의 SharePoint 프로젝트 항목은 콘텐츠 데이터베이스에 추가됩니다.  이러한 추가 어셈블리에 안전 컨트롤과 클래스 리소스를 추가할 수도 있습니다.  안전 컨트롤에 대한 자세한 내용은 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 또는 “Creating a SafeControl Entry” in [Deploying Web Parts in SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=245505). 를 참조하십시오.  
  
#### 기존 어셈블리를 추가하려면  
  
1.  **패키지 디자이너**를 엽니다.  자세한 내용은 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)을 참조하십시오.  
  
2.  **고급** 탭을 선택합니다.  
  
3.  **추가** 단추를 선택한 다음 목록에서 **기존 어셈블리 추가** 를 선택합니다.  
  
     **기존 어셈블리 추가** 대화 상자가 나타납니다.  
  
4.  줄임표\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\)를 선택하고 추가할 어셈블리를 선택합니다.  이식성을 높이려면 선택된 어셈블리의 상대 경로를 사용하는 것이 좋습니다.  
  
5.  전역 어셈블리 캐시에 어셈블리를 배포하려면 **배포 대상** 으로 **GlobalAssemblyCache** 옵션 단추를 선택하고, SharePoint를 실행중인 서버의 WebApplication 폴더에 어셈블리를 배포하려면 **WebApplication** 옵션 단추를 선택합니다.  
  
#### 프로젝트 출력의 어셈블리를 추가하려면  
  
1.  **패키지 디자이너**를 엽니다.  
  
     자세한 내용은 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)을 참조하십시오.  
  
2.  **고급** 탭을 선택합니다.  
  
3.  **추가** 단추를 선택한 다음 목록에서 **프로젝트 출력에서 어셈블리 추가** 를 선택합니다.  
  
     **프로젝트 출력의 어셈블리 추가** 대화 상자가 나타납니다.  
  
4.  **소스 프로젝트** 목럭에서 추가할 소스 프로젝트를 선택합니다.  
  
5.  전역 어셈블리 캐시에 어셈블리를 배포하려면 **배포 대상** 으로 **GlobalAssemblyCache** 옵션 단추를 선택하고, SharePoint를 실행중인 서버의 WebApplication 폴더에 어셈블리를 배포하려면 **WebApplication** 옵션 단추를 선택합니다.  
  
#### 안전 컨트롤을 추가하려면  
  
1.  **기존 어셈블리 편집** 대화 상자를 엽니다.  이것을 완료하려면 패키지 디자이너를 열고 **고급** 탭을 선택한 다음 어셈블리를 선택하고 **편집**단추를 선택합니다.  
  
2.  **안전 컨트롤** 창에서 **새 항목을 추가하려면 여기를 클릭하십시오.** 단추를 선택합니다.  
  
3.  **어셈블리 이름** 열에서 어셈블리의 이름을 입력합니다.  
  
4.  **네임스페이스** 열에서 안전 컨트롤의 네임스페이스 이름을 입력합니다.  
  
5.  **형식 이름** 열에서 형식의 이름을 입력합니다.  
  
#### 클래스 리소스를 추가하려면  
  
1.  **기존 어셈블리 편집** 대화 상자를 엽니다.  이것을 완료하려면 패키지 디자이너를 열고 **고급** 탭을 선택한 다음 어셈블리를 선택하고 **편집** 단추를 선택합니다.  
  
2.  **클래스 리소스** 창에서 **새 항목을 추가하려면 여기를 클릭하십시오.** 단추를 선택합니다.  
  
3.  **파일 이름** 열에서 줄임표\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\)를 선택하고 추가할 클래스 리소스를 선택합니다.  
  
## 사용자 지정 어셈블리 삭제  
 SharePoint 패키지에서 어셈블리를 삭제하거나 기존 어셈블리에서 안전 컨트롤과 클래스 리소스를 삭제할 수 있습니다.  
  
#### 기존 어셈블리를 삭제하려면  
  
1.  **패키지 디자이너**를 엽니다.  자세한 내용은 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)을 참조하십시오.  
  
2.  **고급** 탭을 선택합니다.  
  
3.  **추가 어셈블리** 창에서 삭제할 사용자 지정 어셈블리를 선택합니다.  
  
4.  **삭제** 단추를 선택합니다.  
  
#### 어셈블리에 대한 안전 컨트롤을 삭제하려면  
  
1.  **기존 어셈블리 편집** 대화 상자를 엽니다.  이것을 완료하려면 패키지 디자이너를 열고 **고급** 탭을 선택한 다음 어셈블리를 선택하고 **편집** 단추를 선택합니다.  
  
2.  삭제할 안전 컨트롤을 선택합니다.  
  
3.  Delete 키를 누릅니다.  
  
#### 어셈블리에 대한 클래스 리소스를 삭제하려면  
  
1.  **기존 어셈블리 편집** 대화 상자를 엽니다.  이것을 완료하려면 패키지 디자이너를 열고 **고급** 탭을 선택한 다음 어셈블리를 선택하고 **편집** 단추를 선택합니다.  
  
2.  삭제할 클래스 리소스를 선택합니다.  
  
3.  Delete 키를 누릅니다.  
  
## 참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)   
 [NIB: Building SharePoint Solutions with Team Foundation Server](http://msdn.microsoft.com/ko-kr/700a570a-e98e-4425-aadd-34c014868d43)  
  
  
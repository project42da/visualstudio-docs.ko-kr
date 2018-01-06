---
title: "방법: 추가 어셈블리 추가 및 제거 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.RAD.CustomAssembly
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: d9d1e8db-9df2-4e07-ac8d-59ef05d24090
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8109fade596b15e73234dda378e90c188388e41e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-additional-assemblies"></a>방법: 추가 어셈블리 추가 및 제거
  SharePoint 패키지 기능이 나 데이터를 위한 다른 어셈블리에 의존 하는 경우에 솔루션 패키지 (.wsp)에 어셈블리를 추가할 수 있습니다. 이러한 방식으로 SharePoint 서버에서는 사용자 지정 어셈블리는 패키지와 함께 설치 해야 합니다.  
  
 추가 하 고 안전 컨트롤 및 어셈블리와 관련 된 클래스 리소스 파일을 변경할 수도 있습니다.  
  
## <a name="adding-additional-assemblies-safe-controls-and-class-resources"></a>추가 어셈블리, 안전 컨트롤 및 클래스 리소스 추가  
 SharePoint 솔루션 패키지에 추가 어셈블리를 추가할 수 있습니다. 샌드박스 솔루션의 추가 어셈블리를 전역 어셈블리 캐시에 배포 하지만 샌드박스 솔루션의 프로젝트 항목을 SharePoint 콘텐츠 데이터베이스에 추가 됩니다. 또한 이러한 추가 어셈블리에 안전 컨트롤 및 클래스 리소스를 추가할 수 있습니다. 안전 컨트롤에 대 한 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) 또는에서 "SafeControl 항목 만들기" [SharePoint Foundation의 웹 파트 배포](http://go.microsoft.com/fwlink/?LinkId=245505)합니다.  
  
#### <a name="to-add-an-existing-assembly"></a>기존 어셈블리를 추가 하려면  
  
1.  열기는 **패키지 디자이너**합니다. 자세한 내용은 참조 [하는 방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)합니다.  
  
2.  선택 된 **고급** 탭 합니다.  
  
3.  선택 된 **추가** 단추를 선택한 후 **기존 어셈블리 추가** 목록에서 합니다.  
  
     **기존 어셈블리 추가** 대화 상자가 나타납니다.  
  
4.  줄임표를 선택 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))를 추가 하려는 어셈블리를 선택 합니다. 이식성을 위해 선택한 어셈블리의 상대 경로 사용 하는 것이 좋습니다.  
  
5.  에 대 한는 **배포 대상**, 선택는 **GlobalAssemblyCache** 옵션 단추를 전역 어셈블리 캐시에 어셈블리를 배포 하거나 선택할는 **WebApplication** 옵션 SharePoint를 실행 하는 서버의 WebApplication 폴더에 어셈블리를 배포 하는 단추입니다.  
  
#### <a name="to-add-an-assembly-from-project-output"></a>프로젝트 출력의 어셈블리를 추가 하려면  
  
1.  열기는 **패키지 디자이너**합니다.  
  
     자세한 내용은 참조 [하는 방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)합니다.  
  
2.  선택 된 **고급** 탭 합니다.  
  
3.  선택 된 **추가** 단추를 선택한 후 **프로젝트 출력의 어셈블리 추가** 목록에서 합니다.  
  
     **프로젝트 출력의 어셈블리 추가** 대화 상자가 나타납니다.  
  
4.  에 **소스 프로젝트** 를 나열 하 고 원본 프로젝트를 추가 하려면 선택 합니다.  
  
5.  에 대 한는 **배포 대상**, 선택는 **GlobalAssemblyCache** 옵션 단추를 전역 어셈블리 캐시에 어셈블리를 배포 하거나 선택할는 **WebApplication** 옵션 SharePoint를 실행 하는 서버의 WebApplication 폴더에 어셈블리를 배포 하는 단추입니다.  
  
#### <a name="to-add-a-safe-control"></a>안전 컨트롤을 추가 하려면  
  
1.  열기는 **기존 어셈블리 편집** 대화 상자. 이를 위해 패키지 디자이너를 열고, 선택는 **고급** 탭 어셈블리를 선택한 다음 선택에서 **편집**단추입니다.  
  
2.  에 **안전 컨트롤** 창, 선택는 **새 항목을 추가 하려면 여기를 클릭 하십시오.** 단추입니다.  
  
3.  에 **어셈블리 이름** 열에서 어셈블리의 이름을 입력 합니다.  
  
4.  에 **Namespace** 열 안전 컨트롤에 대 한 네임 스페이스의 이름을 입력 합니다.  
  
5.  에 **유형 이름** 열 형식의 이름을 입력 합니다.  
  
#### <a name="to-add-a-class-resource"></a>클래스 리소스를 추가 하려면  
  
1.  열기는 **기존 어셈블리 편집** 대화 상자. 이를 위해 패키지 디자이너를 열고, 선택는 **고급** 탭 어셈블리를 선택한 다음 선택에서 **편집** 단추입니다.  
  
2.  에 **클래스 리소스** 창, 선택는 **새 항목을 추가 하려면 여기를 클릭 하십시오.** 단추입니다.  
  
3.  에 **파일 이름** 열에서 줄임표를 선택 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")), 클래스 리소스 추가 하려면를 선택 합니다.  
  
## <a name="deleting-custom-assemblies"></a>사용자 지정 어셈블리를 삭제합니다.  
 SharePoint 패키지에서 어셈블리를 삭제 하거나 기존 어셈블리에서 안전 컨트롤 및 클래스 리소스를 삭제할 수 있습니다.  
  
#### <a name="to-delete-an-existing-assembly"></a>기존 어셈블리를 삭제 하려면  
  
1.  열기는 **패키지 디자이너**합니다. 자세한 내용은 참조 [하는 방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)합니다.  
  
2.  선택 된 **고급** 탭 합니다.  
  
3.  에 **추가 어셈블리** 창에서 삭제 하려는 사용자 지정 어셈블리를 선택 합니다.  
  
4.  선택 된 **삭제** 단추입니다.  
  
#### <a name="to-delete-a-safe-control-for-an-assembly"></a>어셈블리에 대 한 안전 컨트롤을 삭제 하려면  
  
1.  열기는 **기존 어셈블리 편집** 대화 상자. 이를 위해 패키지 디자이너를 열고, 선택는 **고급** 탭 어셈블리를 선택한 다음 선택에서 **편집** 단추입니다.  
  
2.  삭제 하려는 안전 컨트롤을 선택 합니다.  
  
3.  Delete 키를 선택 합니다.  
  
#### <a name="to-delete-a-class-resource-for-an-assembly"></a>어셈블리에 대 한 클래스 리소스를 삭제 하려면  
  
1.  열기는 **기존 어셈블리 편집** 대화 상자. 이를 위해 패키지 디자이너를 열고, 선택는 **고급** 탭 어셈블리를 선택한 다음 선택에서 **편집** 단추입니다.  
  
2.  클래스 리소스를 삭제 하려면 선택 합니다.  
  
3.  Delete 키를 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능을 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)   
  
  
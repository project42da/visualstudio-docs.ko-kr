---
title: "방법: 매핑된 폴더 추가 및 제거 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.MappedFolder
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, mapped folders
- mapped folders [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 29809344ee8a3f446589ba84f2fc47b1cf407582
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-and-remove-mapped-folders"></a>방법: 매핑된 폴더 추가 및 제거
  일부 이미지 및 레이아웃 파일 계층 구조에 중첩 되어 같은 폴더에 SharePoint, 일반적으로 사용 합니다. 보다 쉽게 액세스할 하기 위해 SharePoint 프로젝트에 이러한 폴더를 매핑할 수 있습니다. 매핑된 폴더는 SharePoint 프로젝트에 설치 된 SharePoint 서버에서에서 파일의 실제 위치에 해당 하는입니다.  
  
 SharePoint 응용 프로그램을 배포 하면 매핑된 폴더와 그 하위 폴더에서 복사 하는 솔루션 패키지 (.wsp) 서버에 모두의 내용을 실행 되는 SharePoint의 SharePoint 폴더 트리에서 지정된 된 위치에. 이 위치에 의해 결정 됩니다는 **배포 위치** 매핑된 폴더에 대해 설정 된 속성입니다. 매핑된 폴더에 하위 폴더에 상대적인는 **배포 위치** 매핑된 폴더의 합니다. **배포 위치** 매핑된 폴더의 이름이 아니라 속성 항목 배포 되는 위치를 결정 합니다.  
  
 프로젝트에 대 한 메뉴 모음이 나 바로 가기 메뉴에서 명령을 사용 하 여 프로젝트에 매핑된 폴더를 추가할 수 있습니다. 사용할 수는 **추가 SharePoint "이미지" 매핑된 폴더** 및 **추가 SharePoint "레이아웃" 폴더** 매핑된 가장 자주 사용 되는 폴더를 추가 하는 것입니다. 매핑할 수 있습니다 다른 사용 가능한 SharePoint 폴더의 프로젝트를 사용 하 여는 **SharePoint 매핑된 폴더 추가** 바로 가기 메뉴 명령을 클릭 한 다음 폴더를 지정 하는 **SharePoint 매핑된 폴더 추가** 대화 상자.  
  
## <a name="adding-mapped-folders-to-a-project"></a>프로젝트에 매핑된 폴더 추가  
 다음 절차에는 비주얼 웹 파트 프로젝트에 매핑된 두 개의 폴더를 추가 하는 방법을 설명 합니다. 를 시작 하려면 비주얼 웹 파트 프로젝트를 만들 수 있습니다.  
  
#### <a name="to-add-mapped-folders-to-a-project"></a>프로젝트에 매핑된 폴더를 추가 하려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 하나는 **Visual Basic** 또는 **Visual C#** 노드를 확장 하 고는 **Office/SharePoint** 노드를 선택한 다음 선택 된 **SharePoint 솔루션** 노드.  
  
3.  프로젝트 템플릿 목록에서 선택 된 **SharePoint 2013 비주얼 웹 파트** 템플릿.  
  
4.  에 **이름** 상자에 입력 **TestProject1**, 선택한 후는 **확인** 단추입니다.  
  
5.  에 **SharePoint 사용자 지정 마법사**, 선택는 **마침** 단추 기본 설정을 유지 합니다.  
  
6.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **추가 SharePoint "이미지" 매핑된 폴더**합니다.  
  
     명명 된 폴더 **이미지** 프로젝트에 표시 되 고 TestProject1 라는 하위 폴더를 포함 합니다. 이 매핑된 폴더에는 비주얼 웹 파트 프로젝트에 대 한 이미지가 포함 됩니다.  
  
7.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **SharePoint 매핑된 폴더 추가** 표시 하는 **추가 SharePoint 매핑된 폴더** 대화 상자.  
  
8.  매핑에 사용할 수 있는 폴더의 트리 뷰에서 선택 된 **리소스** 폴더를 선택한 후는 **확인** 단추입니다.  
  
     명명 된 폴더 **리소스** 프로젝트에 나타납니다. 이 폴더는 문자열 리소스 파일 등의 항목을 저장할 수 있습니다. 하위 폴더는 매핑된 폴더의 내용을 구성 하는 데 유용할 수 있지만 사용 하 여 매핑된 폴더를 추가할 때 자동으로 만들어져는 **SharePoint 매핑된 폴더 추가** 명령입니다. 하위 폴더를 추가 하려면 선택은 **리소스** 폴더를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 폴더**합니다.  
  
## <a name="changing-the-deployment-location-of-a-mapped-folder"></a>매핑된 폴더의 배포 위치를 변경합니다.  
 기본적으로 토큰 {SharePointRoot} 나타냅니다는 SharePoint 루트 설치 경로 기준으로 특정 위치에 매핑된 폴더 추가 됩니다. 그러나 변경 하 여이 위치를 변경할 수는 **배포 위치** 매핑된 폴더의 속성입니다. 각 매핑된 폴더에는 자체 **배포 위치** 속성입니다.  
  
#### <a name="to-change-the-deployment-location-of-a-mapped-folder"></a>매핑된 폴더의 배포 위치를 변경 하려면  
  
1.  앞에서 만든 프로젝트에 매핑된 폴더를 선택 합니다.  
  
2.  에 **속성** 창에서 줄임표를 선택 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")) 단추는 **배포 위치** 속성입니다.  
  
3.  에 **SharePoint 매핑된 폴더 추가** 대화 상자 가리키도록 매핑된 폴더 폴더를 찾습니다.  
  
4.  노드를 선택 하 고 선택 된 **확인** 단추입니다.  
  
## <a name="renaming-or-removing-mapped-folders"></a>매핑된 폴더 이름 바꾸기 또는 제거  
  
#### <a name="to-rename-or-remove-a-mapped-folder"></a>매핑된 폴더를 제거 하거나 이름을 변경 하려면  
  
1.  앞에서 만든 프로젝트에 매핑된 폴더를 선택 합니다.  
  
2.  매핑된 폴더의 이름을 바꾸려면 해당 바로 가기 메뉴를 열고 **이름 바꾸기**새 이름을 입력 하 고 Enter 키를 선택 합니다.  
  
     대신, 이름 바꾸기을 열고 원하는 매핑된 폴더를 선택할 수 있습니다는 **속성** 창에서 다음의 값을 설정 하 고는 **폴더 이름** 속성을 새 이름입니다.  
  
3.  매핑된 폴더를 프로젝트에서 제거 하려면 해당 바로 가기 메뉴를 열고 **삭제**를 선택한 후는 **확인** 제거를 확인 하는 대화 상자에서 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  
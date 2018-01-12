---
title: "방법: 부호 안전 컨트롤로 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- SharePoint development in Visual Studio, advanced packaging tools
- safe controls [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9d34722f7dc9b9975429fac64311dd0b63c30fbe
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-mark-controls-as-safe-controls"></a>방법: 컨트롤을 안전 컨트롤로 표시
  보안을 위해 SharePoint를 스크립트 삽입 으로부터 보호 되는 웹 컨트롤 및 되지 않는 구분 합니다. 컨트롤, 보호 또는 *안전 컨트롤*, 신뢰할 수 없는 사용자가 액세스할 수 있습니다. SharePoint 프로젝트 항목의 또는 안전 컨트롤 항목 속성에 안전한 것으로 컨트롤을 표시할 수 있습니다는 **패키지 디자이너** 패키지에 어셈블리를 추가 하면 됩니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 [web.config 파일 설정 변경](http://go.microsoft.com/fwlink/?LinkId=178965) 및 [웹 파트 어셈블리를 Safe 컨트롤로 등록](http://go.microsoft.com/fwlink/?LinkId=171013)합니다.  
  
> [!IMPORTANT]  
>  이러한 절차는 설명 목적입니다. 표시 제어 안전 하다는 확신 하는 경우에 가능 합니다.  
  
## <a name="marking-safe-controls-in-the-safe-control-entries-property"></a>안전 컨트롤 항목 속성에서 안전 컨트롤 표시  
  
#### <a name="to-mark-controls-as-safe-or-unsafe-in-the-safe-control-entries-property"></a>개체를 안전 하 게 보호 또는 안전 컨트롤 항목 속성에서 안전 하지 않은 컨트롤 표시  
  
1.  비주얼 웹 파트 프로젝트와 함께 SharePoint 솔루션을 만듭니다.  
  
2.  웹 파트에 두 개의 추가: 텍스트 상자와 단추가 있습니다. 각각의 기본값을 TextBox1 및 Button1 이름을 둡니다.  
  
3.  두 항목을 웹 파트의 추가 **안전 컨트롤 항목** 속성입니다. 이 작업을 수행 하려면 줄임표를 선택 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")) 단추 옆에 **안전 컨트롤 항목** 는 에서속성 **속성** 창.  
  
     **안전 컨트롤 항목** 대화 상자가 나타납니다.  
  
4.  **안전 컨트롤 항목** 대화 상자에서 선택 하는 **추가** 두 안전 컨트롤 항목을 추가 하려면 두 번 단추는 **멤버** 창: 단추와 텍스트 상자에 대 한 합니다.  
  
5.  첫 번째 안전 컨트롤 항목을 선택 하 고 다음 값을 변경 해당 **안전** 속성을 **False**, 해당 **유형 이름** 속성을 **Button1**, 및 해당 **스크립트에 대해 안전** 속성을 **False**합니다.  
  
     이 단계는 안전 하지 않은 컨트롤로 단추 컨트롤을 식별합니다.  
  
6.  목록에서 두 번째 안전 컨트롤 항목을 선택합니다. 값을 지정 하지는 **안전** 속성으로 **True** 설정 하 고 해당 **유형 이름** 속성을 **TextBox1** 및 해당 **안전 하 게 보호 스크립트에 대해** 속성을 **True**합니다.  
  
     텍스트 상자 컨트롤은 스크립트 삽입에 대해 안전 컨트롤로 표시 됩니다.  
  
7.  **확인** 단추를 선택하여 대화 상자를 닫습니다.  
  
## <a name="marking-safe-controls-in-the-package-designer"></a>패키지 디자이너에서 안전 컨트롤 표시  
  
#### <a name="to-mark-controls-as-safe-or-unsafe-in-the-package-designer"></a>안전한 것 이나 패키지 디자이너에서 안전 하지 않은 컨트롤 표시 하려면  
  
1.  비주얼 웹 파트 프로젝트와 함께 SharePoint 솔루션을 만듭니다.  
  
2.  웹 파트에 두 개의 추가: 텍스트 상자와 단추가 있습니다. 각각의 기본값을 TextBox1 및 Button1 이름을 둡니다.  
  
     나중에 사용 하기 때문에 컨트롤의 네임 스페이스를 기록해 둡니다.  
  
3.  메뉴 모음에서 **빌드**, **솔루션 빌드** 프로젝트를 빌드합니다.  
  
4.  다른 SharePoint 솔루션을 만듭니다.  
  
5.  **솔루션 탐색기**를 Package.Package 파일에 대 한 바로 가기 메뉴를 열고 다음을 선택 **열고** 열려는 **패키지 디자이너**합니다.  
  
6.  에 **패키지 디자이너**, 선택는 **고급** 탭 합니다.  
  
7.  아래 **추가 어셈블리**, 선택는 **추가** 단추를 선택한 후 **기존 어셈블리 추가** 목록에서 합니다.  
  
8.  에 **기존 어셈블리 추가** 대화 상자에서 줄임표 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")) 단추 옆에  **소스 경로**합니다.  
  
9. 1 단계에서에서 만든 SharePoint 솔루션에서 어셈블리를 선택 하 고 선택 된 **열려** 단추입니다.  
  
10. 이 예제에서는 상태로 둡니다는 **배포 대상** GlobalAssemblyCache로 옵션입니다.  
  
     이 단계를 수행 하면 어셈블리를 시스템 전역 어셈블리 캐시 (GAC)에 배포 합니다. 웹 응용 프로그램 (Bin) 폴더에 배포 되도록 어셈블리를 사용 하도록 하려는 경우 해당 옵션을 선택 합니다. 자세한 내용은 참조 [SharePoint Foundation의 웹 파트 배포](http://go.microsoft.com/fwlink/?LinkId=177509)합니다.  
  
11. 에 **안전 컨트롤** 상자는 **새 항목을 추가 하려면 여기를 클릭 하십시오.** 단추입니다.  
  
12. 다음 표에 속성에 대 한 값을 입력 합니다.  
  
    |속성 이름|값|  
    |-------------------|-----------|  
    |네임스페이스|컨트롤에 대 한 정규화 된 네임 스페이스와 같은 **BdcModelProject1.VisualWebPart1**합니다.|  
    |형식 이름|Button1|  
    |어셈블리 이름|와 같은 강력한 어셈블리 이름을: Microsoft.Office.SharePoint.ClientExtensions, 버전 14.0.0.0, Culture = neutral, PublicKeyToken = 71e9bce111e9429c = 합니다.|  
    |안전|지우기는 **안전** 확인란 합니다.|  
    |스크립트에 대해 안전|유지 된 **스크립트에 대해 안전** 확인란을 선택 취소 합니다.|  
  
    > [!NOTE]  
    >  **어셈블리 이름** 통해 추가 된 어셈블리에 대 한 값은 **고급** 탭은 **패키지 디자이너** 수 없는 토큰 일 것 강력한 이름의 어셈블리 합니다. 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](http://go.microsoft.com/fwlink/?LinkId=177513)을 참조하세요.  
  
13. 탭 키를 선택하여 다른 안전 컨트롤 항목을 만듭니다.  
  
14. 선택 된 **새 항목을 추가 하려면 여기를 클릭 하십시오.** 단추를 다시 합니다.  
  
15. 다음 표에 속성에 대 한 값을 입력 합니다.  
  
    |속성 이름|값|  
    |-------------------|-----------|  
    |네임스페이스|컨트롤에 대 한 정규화 된 네임 스페이스와 같은 **BdcModelProject1.VisualWebPart1**합니다.|  
    |형식 이름|TextBox1|  
    |어셈블리 이름|와 같은 강력한 어셈블리 이름을: Microsoft.Office.SharePoint.ClientExtensions, 버전 14.0.0.0, Culture = neutral, PublicKeyToken = 71e9bce111e9429c = 합니다.|  
    |안전|선택 된 **안전** 확인란 합니다.|  
    |스크립트에 대해 안전|선택 된 **스크립트에 대해 안전** 확인란 합니다.|  
  
16. Tab 키를 선택 하 고 선택 된 **확인** 단추 대화 상자를 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [패키지 및 프로젝트 항목에 대 한 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  
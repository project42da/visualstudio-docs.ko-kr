---
title: "방법: SharePoint 솔루션 패키지 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.RAD.PackageDesignerAdvanced
- VS.SharePointTools.RAD.PackageDesigner.Manifest
- VS.SharePointTools.RAD.PackageDesignerProperties
- VS.SharePointTools.RAD.PackageDesigner.SwitchView
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 277ceea1b908c5819608a1bdf1d6be97c2f6ce77
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-customize-a-sharepoint-solution-package"></a>방법: SharePoint 솔루션 패키지 사용자 지정
  패키지 디자이너를 사용 하 여를 만들고 패키지 (.wsp)를 사용자 지정할 수 있습니다. 예를 들어 웹 서버의 솔루션이 배포 될 때 다시 설정 및 배포 서버 유형을 설정 하는 경우 지정할에 SharePoint 프로젝트 항목 및 기능을 추가할 수 있습니다.  
  
## <a name="opening-the-package-designer"></a>패키지 디자이너 열기  
  
#### <a name="to-open-the-package-designer"></a>패키지 디자이너를 열려면  
  
-   **솔루션 탐색기**를 두 번 클릭 **패키지**, 선택 또는 **뷰 디자이너** 에 대 한 바로 가기 메뉴에서 **패키지**합니다.  
  
## <a name="viewing-the-packaged-manifest-file"></a>패키지 매니페스트 파일 보기  
 패키지 디자이너를 사용 하 여 수정 하 고 패키지 매니페스트 파일을 생성할 수 있습니다. 그런 다음 Visual Studio에서이 파일에 대 한 XML 코드를 볼 수 있습니다.  
  
#### <a name="to-view-the-xml-source-file"></a>XML 소스 파일을 보려면  
  
1.  에 **패키지 디자이너**, 선택 **매니페스트**합니다.  
  
#### <a name="to-view-the-packaged-manifest-file-by-using-solution-explorer"></a>솔루션 탐색기를 사용 하 여 패키지에 포함 된 매니페스트 파일을 보려면  
  
1.  **솔루션 탐색기**, 선택 **모든 파일 표시**합니다.  
  
2.  패키지를 확장 하 고 있습니다. 패키지를 확장 한 다음 Package.Template.xml 파일을 엽니다.  
  
    > [!NOTE]  
    >  패키지 템플릿의 매니페스트 XML 파일을 열 때 파일 자동으로 확인 되 면 하 고 오류 목록 창에 표시 되는 경고를 무시할 수 있습니다.  
  
## <a name="changing-the-manifest-template"></a>매니페스트 템플릿 변경  
 Visual Studio XML 편집기 또는 매니페스트 템플릿 창에서 패키지에 포함 된 매니페스트 파일에 대 한 XML 코드를 변경할 수 있습니다. XML 코드를 변경 패키지에 대 한 패키지 매니페스트 파일에 병합 됩니다.  
  
#### <a name="to-change-the-manifest-template-by-using-the-xml-editor"></a>XML 편집기를 사용 하 여 매니페스트 템플릿을 변경 하려면  
  
1.  에 **패키지 디자이너**, 선택는 **매니페스트** 탭을 확장 하 고는 **옵션 편집** 노드를 선택한 후는 **XML 편집기에서 열리지** 링크 합니다.  
  
     패키지 매니페스트 파일에 XML 변경 내용이 병합 됩니다.  
  
#### <a name="to-change-the-manifest-template-by-using-the-manifest-template-pane"></a>매니페스트 템플릿 창을 사용 하 여 매니페스트 템플릿을 변경 하려면  
  
1.  에 **패키지 디자이너**, 선택는 **매니페스트** 탭을 확장 하 고는 **옵션 편집** 노드를 선택한 다음 변경 매니페스트 템플릿 창에 표시 되는 XML입니다.  
  
     변경 내용이 XML에 표시 된 **패키지 매니페스트 미리 보기** 창.  
  
## <a name="overwriting-the-packaged-manifest-file"></a>패키지에 포함 된 매니페스트 파일을 덮어쓰는  
 패키지 디자이너를 사용 하지 않도록 설정 하 고 manifest.xml 파일을 수동으로 만들 수 있습니다. 이 절차를 수행 하는 처음으로 패키지 디자이너의 현재 설정은 패키지 템플릿 XML 파일에 저장 됩니다. 그런 다음 수정 하거나 XML 코드를 덮어쓸 수 있습니다.  
  
> [!NOTE]  
>  를 추가 하거나 패키지 디자이너를 사용 하지 않도록 설정 하는 동안 XML 파일에서 SharePoint 프로젝트 항목 및 기능을 제거 하는 경우 이러한 프로젝트 항목 및 기능은 패키지 되지 않습니다.  
  
#### <a name="to-overwrite-packaged-manifest-file-by-disabling-the-designer"></a>디자이너를 사용 하지 않도록 설정 하 여 패키지에 포함 된 매니페스트 파일을 덮어쓸 수  
  
1.  에 **패키지 디자이너**, 선택는 **매니페스트** 탭 합니다.  
  
2.  이어야 합니다.  
  
3.  확장의 **옵션 편집** 노드를 선택는 **덮어쓰기 생성 된 XML과 편집 편집기에서 매니페스트 XML** 링크를 선택한 후는 **예** 단추입니다.  
  
     서식 파일은 현재 패키지에 포함 된 매니페스트 파일로 업데이트 됩니다.  
  
## <a name="enabling-the-package-designer"></a>패키지 디자이너를 사용 하도록 설정  
 Manifest.xml 파일 사용자 지정 하려면 패키지 디자이너를 다시 설정할 수 있습니다.  
  
#### <a name="to-re-enable-the-designer"></a>디자이너를 다시 활성화 하려면  
  
1.  에 **패키지 디자이너**, 선택는 **매니페스트 편집 내용을 취소 하 고 디자이너를 다시 설정** 링크를 선택한 후는 **예** 단추입니다.  
  
     서식 파일은 원래 텍스트와 새로 고쳐지고 XML 변경 내용은 모두 손실 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  
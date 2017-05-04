---
title: "방법: BDC 기능에 사용자 지정 어셈블리 포함 | Microsoft Docs"
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
  - "VS.SharePointTools.BDC.Add_Assemblies_Dialog"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 참조 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], 사용자 지정 어셈블리"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 참조 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 사용자 지정 어셈블리"
ms.assetid: 2ddf44b9-5f51-4bca-b8bb-94c4bbd1c5f3
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: BDC 기능에 사용자 지정 어셈블리 포함
  프로젝트에서 동일한 솔루션의 다른 프로젝트에 있는 어셈블리를 참조할 수 있습니다.  그러나 이렇게 어셈블리를 참조하려면 **참조된 어셈블리를 LobSystem에 할당** 대화 상자를 사용하여 프로젝트의 기능 파일에 해당 어셈블리를 추가해야 합니다.  
  
### BDC\(비즈니스 데이터 연결\) 기능에 사용자 지정 어셈블리를 포함하려면  
  
1.  **솔루션 탐색기**에서 BDC 모델이 들어 있는 폴더를 선택합니다.  
  
2.  **보기** 메뉴에서 **속성 창**을 클릭합니다.  
  
3.  **속성** 창에서 **어셈블리** 속성을 선택하고 줄임표 단추\(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\)를 선택합니다.  
  
     **참조된 어셈블리를 LobSystem에 할당** 대화 상자가 나타납니다.  
  
4.  **어셈블리 선택** 목록에서 사용자 지정 어셈블리를 선택 합니다.  
  
    > [!NOTE]  
    >  어셈블리가 포함된 프로젝트에 대한 참조를 추가한 경우에만 **참조된 어셈블리를 LobSystem에 할당** 대화 상자에 어셈블리가 표시됩니다.  자세한 내용은 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)을 참조하십시오.  
  
5.  **참조 속성** 그룹에서, **LobSystem 범위** 속성에 대해 표시된 드롭다운 목록을 열고, 사용자 지정 어셈블리를 사용하는 LOB 시스템을 선택한 다음, **OK** 버튼을 선택합니다.  
  
    > [!NOTE]  
    >  사용자 지정 어셈블리의 코드를 디버깅하려면 해당 어셈블리를 솔루션 패키지에 추가해야 합니다.  자세한 내용은 [방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: 리소스 파일을 사용하여 지역화된 이름, 속성 및 사용 권한 지정](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  
---
title: "방법: 기능 종속성 추가 및 제거 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW
- VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, features
ms.assetid: 2b34c8d9-c975-4fe9-b8e0-52db4a6014ea
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d758c5d4f410881989492f64dd7a7e5b8dc73804
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-and-remove-feature-dependencies"></a>방법: 기능 종속성 추가 및 제거
  SharePoint 기능이 기능이 나 데이터에 대 한 다른 기능을 사용할 수 있습니다. 이러한 경우 프로그램 기능에 대 한 종속성으로 이러한 다른 기능을 표시할 수 있습니다. 이러한 방식으로 SharePoint server를 사용 하면 기능이 활성화 되기 전에 종속 기능이 활성화 됩니다.  
  
## <a name="adding-dependencies"></a>종속성 추가  
 종속성으로 솔루션의 다른 기능을 추가할 수 있습니다. 이러한 방식으로 만들면 필요한 기능이 설치 되 고 기능을 설치 하기 전에 활성화 되었는지 됩니다.  
  
#### <a name="to-add-a-dependency-on-a-feature-in-the-solution"></a>기능 솔루션에 대 한 종속성을 추가 하려면  
  
1.  기능 디자이너를 열고는 **기능 활성화 종속성** 노드를 선택한 후는 **추가** 단추입니다.  
  
2.  에 **기능 활성화 종속성 추가** 대화 상자에서 선택 하는 **솔루션 기능에에서 대 한 종속성 추가** 옵션 단추를 선택을 종속성으로 추가 하려는 기능의 제목 한 다음 선택 된 **추가** 단추입니다.  
  
     Ctrl 키를 선택 하는 동안 여러 타이틀을 선택 하 여 둘 이상의 기능을 추가할 수 있습니다.  
  
## <a name="adding-custom-dependencies"></a>사용자 지정 종속성 추가  
 종속 항목으로 SharePoint 서버에 이미 배포 되어 있는 기능을 추가할 수 있습니다. 이러한 방식으로 SharePoint 활성화 프로세스에서 확인 기능을 설치 하기 전에 모든 종속 기능이 활성화 되 고 있는지 확인 합니다.  
  
#### <a name="to-add-a-dependency-by-the-feature-id"></a>기능 ID로 종속성을 추가 하려면  
  
1.  기능 디자이너를 열고는 **기능 활성화 종속성** 노드를 선택한 후는 **추가** 단추입니다.  
  
2.  에 **기능 활성화 종속성 추가** 대화 상자에서 선택 하는 **사용자 지정 종속성을 추가** 옵션 단추입니다.  
  
3.  에 **기능 ID** 텍스트 상자에 활성화 종속성으로 표시 하 고 다음을 선택 하려는 기능에 대 한 GUID를 입력 합니다는 **추가** 단추입니다.  
  
## <a name="editing-custom-dependencies"></a>사용자 지정 종속성 편집  
 이전에 추가한 사용자 지정 종속성을 편집할 수 있습니다. 그러나으로 솔루션만 수, 제거 된 종속 기능 편집할 수 없습니다.  
  
#### <a name="to-change-a-dependency-on-a-feature-in-the-solution"></a>솔루션의 기능에 대 한 종속성을 변경 하려면  
  
1.  기능 디자이너를 열고 확장 한 다음 확장은 **기능 활성화 종속성** 노드.  
  
2.  편집한 다음 선택할 하려는 기능의 이름을 선택 된 **편집** 단추입니다.  
  
3.  에 **사용자 지정 기능 활성화 종속성 편집** 대화 상자, 제목, 기능 ID 또는 설명 변경 선택한 후는 **전송** 단추입니다.  
  
## <a name="removing-dependencies"></a>종속성 제거  
  
#### <a name="to-remove-a-dependency-on-a-feature-in-the-solution"></a>솔루션의 기능에 대 한 종속성을 제거 하려면  
  
1.  기능 디자이너에서 확장의 **기능 활성화 종속성** 노드를 제거한 다음 선택 하려는 기능의 이름을 선택는 **제거** 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능을 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  
---
title: BDC 모델 디자인 도구 개요 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.Method_Details
- VS.SharePointTools.BDC.Explorer
- VS.SharePointTools.BDC.Diagram
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], method details
- Business Data Connectivity service [SharePoint development in Visual Studio], designer
- Business Data Connectivity service [SharePoint development in Visual Studio], method details
- BDC [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], designer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 11469e76464cf4177d581705004bf640d71c43a1
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691481"
---
# <a name="bdc-model-design-tools-overview"></a>BDC 모델 디자인 도구 개요
  BDC 디자이너를 사용 하 여 비즈니스 데이터 BDC (연결) 모델을 디자인할 수는 **BDC 메서드 세부 정보** 창 및 **BDC 탐색기**합니다.  
  
 **BDC 탐색기** 모델을 탐색 하 고 검색 하 고, 형식 설명자를 정의할 수 있습니다.  
  
## <a name="bdc-designer"></a>BDC 디자이너
 BDC 디자이너를 사용 하면 모델의 엔터티를 정의 하 고 서로 간의 관계를 시각적으로 정렬할 수 있습니다. BDC 디자이너를 사용 하 여 다음 작업을 수행 합니다.  
  
-   모델에 엔터티를 추가 합니다.  
  
-   모델에서 엔터티를 제거 합니다.  
  
-   엔터티 간의 관계를 정의 합니다.  
  
 BDC 디자이너를 열려면 프로젝트에 모델 파일을 두 번 클릭 하거나 모델 파일에 대 한 바로 가기 메뉴를 열고 선택한 후 **열고**합니다. 엔터티를 끌거나 복사 하 여 모델에 추가 **엔터티** 에서 **도구 상자** 디자이너에 끌어 합니다. 두 엔터티 간의 연결을 만들려면 선택 된 **연결** 컨트롤에 **도구 상자**첫 번째 엔터티를 선택한 다음 두 번째 엔터티를 선택 합니다.  
  
## <a name="bdc-method-details-window"></a>BDC 메서드 세부 정보 창
 사용 하 여는 **BDC 메서드 세부 정보** 창의 매개 변수 인스턴스를 정의 하 고 필터 메서드 설명자입니다.  
  
 Finder, 특정 Finder, 작성자, 업데이트 프로그램 및 Deleter 메서드를 빠르게 생성할 수 있습니다는 **BDC 메서드 세부 정보** 창. 이러한 메서드를 생성 하는 경우 Visual Studio 메서드에 매개 변수, 인스턴스 및 형식 설명자, 등의 메타 데이터를 추가 합니다. 특정 시나리오를 충족 하기 위해이 메타 데이터를 수정할 수 있습니다.  
  
 열려는 **BDC 메서드 세부 정보** 창, 메뉴 모음에서 선택 **보기**, **다른 창**, **BDC 메서드 세부 정보**합니다.  
  
 메서드를 보려면는 **BDC 메서드 세부 정보** 창 BDC 디자이너에서 엔터티를 선택 합니다. 선택 된 엔터티 메서드가에 표시 된 **BDC 메서드 세부 정보** 창. BDC 디자이너에서 엔터티를 선택 하지 않으면는 **BDC 메서드 세부 정보** 창 없는 정보를 표시 합니다.  
  
 노드를 축소 또는 확장 하 고는 **BDC 메서드 세부 정보** 필터 설명자 및 매개 변수 인스턴스를 정의 하는 창입니다. 사용 하 여는 **BDC 탐색기** 형식 설명자를 정의할 수 있습니다.  
  
## <a name="bdc-explorer"></a>BDC 탐색기
 **BDC 탐색기** 모델을 구성 하는 요소를 표시 합니다. 열려는 **BDC 탐색기**, 메뉴 모음에서 **보기**, **다른 창**, **BDC 탐색기**합니다. 노드를 확장 된 모델을 검색 하는 **BDC 탐색기**합니다. 각 노드에 모델 파일의 XML에서 요소를 나타냅니다.  
  
 에 대 한 노드를 선택 하 여는 **BDC 탐색기**에 선택 하는 각 노드의 속성이 표시는 **속성** 창. 이러한 속성 중 대부분의 모델 파일의 특성에 해당합니다. 맨 위에 있는 검색 상자를 사용 하 여 모델을 검색할 수는 **BDC 탐색기**합니다.  
  
> [!NOTE]  
>  **BDC 탐색기** 식별자, 사용자 지정 속성, 지역화 된 문자열, 연결 그룹, 작업, 필터 설명자, 작업 제어 목록 및 기본 매개 변수 값 표시 되지 않습니다.  
  
### <a name="define-type-descriptors"></a>형식 설명자를 정의 합니다.
 사용 하 여는 **BDC 탐색기** 형식 설명자를 정의할 수 있습니다. BDC 탐색기를 사용 하면 형식 설명자를 한 번만 정의 하 고 다음 모델의 다른 위치에서 해당 형식 설명자를 다시 사용할 수 있습니다. 이를 위해 복사 형식 설명자를 다른 매개 변수를 붙여 넣거나 형식 설명자입니다.  
  
> [!NOTE]  
>  원래 형식 설명자에 대 한 변경에는 해당 형식 설명자의 복사본은 영향을 주지 않습니다.  
  
 자세한 내용은 참조 [하는 방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)합니다.  
  
## <a name="see-also"></a>참고자료
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: 특정 Finder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)   
 [연습: 비즈니스 데이터를 사용 하 여 SharePoint에 외부 목록 만들기](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
 
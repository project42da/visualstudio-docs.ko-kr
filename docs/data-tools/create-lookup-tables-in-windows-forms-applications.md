---
title: "Windows Forms 응용 프로그램에서 조회 테이블 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lookup tables
- lookup tables, creating
ms.assetid: 0edd5385-c381-4b17-9096-74e2778db9d5
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: f27fdbe216b6ba2a738f6d9f45d746344d542b38
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="create-lookup-tables-in-windows-forms-applications"></a>Windows Forms 응용 프로그램에서 조회 테이블 만들기
용어 *조회 테이블* 두 관련된 데이터 테이블에 바인딩되는 컨트롤에 설명 합니다. 이러한 조회 컨트롤에는 두 번째 테이블에서 선택한 값에 따라 첫 번째 테이블의에서 데이터를 표시 합니다.  
  
 부모 테이블의 기본 노드 드래그 하 여 조회 테이블을 만들 수 있습니다 (에서 [데이터 소스 창](add-new-data-sources.md)) 관련된 자식 테이블의 열에 이미 바인딩되어 있는 폼의 컨트롤로 합니다.  
  
 예를 들어 테이블이 있다고 가정할 `Orders` 판매 데이터베이스에서 합니다. 각 레코드는 `Orders` 테이블에는 `CustomerID`, 고객 주문을 나타내는입니다. `CustomerID` 에서 고객 레코드를 가리키는 외래 키의 `Customers` 테이블입니다. 이 시나리오에서 확장 된 `Orders` 테이블에 **데이터 원본** 창 주 노드를 설정 하 고 **세부 정보**합니다. 다음 설정의 `CustomerID` 사용할 열을는 <xref:System.Windows.Forms.ComboBox> (또는 다른 컨트롤을 지 원하는 조회 바인딩) 끌어서는 `Orders` 노드를 폼으로 합니다. 마지막으로 끌어는 `Customers` 노드 관련된 열에 바인딩된 컨트롤으로-이 경우는 <xref:System.Windows.Forms.ComboBox> 에 바인딩된는 `CustomerID` 열입니다.  
  
## <a name="to-databind-a-lookup-control"></a>데이터 바인딩에 조회 컨트롤  
  
1.  열기는 **데이터 소스** 창.  
  
    > [!NOTE]
    >  조회 테이블을 사용 하려면 두 개의 관련된 테이블이 나 개체는 사용할 수는 **데이터 소스** 창. 자세한 내용은 참조 [데이터 집합의 관계](relationships-in-datasets.md)합니다.  
  
2.  노드를 확장 하 고는 **데이터 소스** 부모 테이블과 부모 테이블의 모든 열 및 관련된 자식 테이블의 모든 열 표시 될 때까지 창.  
  
    > [!NOTE]
    >  자식 테이블 노드는 부모 테이블의 확장 가능한 자식 노드로 표시 되는 노드입니다.  
  
3.  자식 테이블의 놓기 형식을 변경 **세부 정보** 선택 하 여 **세부 정보** 자식 테이블 노드의 컨트롤 목록에서 합니다. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
4.  두 테이블을 연결 하는 노드를 찾습니다 (의 `CustomerID` 이전 예에서 노드). 놓기 형식을 변경 하는 <xref:System.Windows.Forms.ComboBox> 선택 하 여 **ComboBox** 컨트롤 목록에서 합니다.  
  
5.  기본 자식 테이블 노드를 끌어는 **데이터 소스** 창에서 폼으로 합니다.  
  
     설명 레이블이) (있는 데이터 바인딩된 컨트롤이 도구 스트립 (<xref:System.Windows.Forms.BindingNavigator>) 폼에 나타납니다. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다.  
  
6.  기본 부모 테이블 노드를 끌어는 **데이터 원본** 조회 컨트롤에 직접 드롭하면 창 (의 <xref:System.Windows.Forms.ComboBox>).  
  
     이제 조회 바인딩은 설정 됩니다. 컨트롤에 설정 된 특정 속성에 대 한 아래 표를 참조 하십시오.  
  
    |속성|설정 설명|  
    |--------------|----------------------------|  
    |**데이터 원본**|Visual Studio는 사용자가 컨트롤로 끌어 온 테이블에 대해 작성된 <xref:System.Windows.Forms.BindingSource>로 이 속성을 설정합니다. 컨트롤을 만들 때 작성된 <xref:System.Windows.Forms.BindingSource>가 아닙니다.<br /><br /> 조정이 필요한 경우 그런 다음이 설정는 <xref:System.Windows.Forms.BindingSource> 표시 하려는 열이 있는 테이블입니다.|  
    |**DisplayMember**|Visual Studio는 컨트롤로 끄는 테이블에 대해 문자열 데이터 형식을 포함하는 기본 키 다음의 첫 번째 열로 이 속성을 설정합니다.<br /><br /> 조정이 필요한 경우 표시 하려는 열 이름으로 설정 합니다.|  
    |**ValueMember**|Visual Studio는 이 속성을 기본 키에 포함되는 첫 번째 열로 설정하거나 키가 정의되어 있지 않으면 테이블의 첫 번째 열로 설정합니다.<br /><br /> 조정이 필요한 경우 표시 하려는 열이 있는 테이블의 기본 키로 설정 합니다.|  
    |**SelectedValue**|삭제할 원래 열에이 속성을 설정 하는 visual Studio는 **데이터 소스** 창.<br /><br /> 조정이 필요한 경우 관련된 테이블의 외래 키 열으로 설정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
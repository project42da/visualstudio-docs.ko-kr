---
title: "데이터 집합 및 Tableadapter를 다른 프로젝트로 분리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, separating Datasets and TableAdapters
ms.assetid: f66a3940-6227-46af-a930-9177f425f4fd
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 4ae00a8b3a51b088100d4a27893dd100d5d7ba71
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="separate-datasets-and-tableadapters-into-different-projects"></a>별도 데이터 집합 및 Tableadapter 다른 프로젝트로
형식화 된 데이터 집합 향상 된 있도록는 [Tableadapter](create-and-configure-tableadapters.md) 및 별도 프로젝트로 dataset 클래스를 생성할 수 있습니다. 따라서 빠르게 응용 프로그램 계층을 분리 하 고 n 계층 데이터 응용 프로그램을 생성할 수 있습니다.  
  
다음 절차에서는 사용 하는 **데이터 집합 디자이너** 생성된 된 TableAdapter 코드를 포함 하는 프로젝트와에서 별개의 프로젝트로 데이터 집합 코드를 생성 합니다.  
  
## <a name="separate-datasets-and-tableadapters"></a>별도 데이터 집합 및 Tableadapter  
TableAdapter 코드에서 데이터 집합 코드를 분리 하는 경우에 데이터 집합 코드를 포함 하는 프로젝트 현재 솔루션에 있어야 합니다. 이 프로젝트가 현재 솔루션에 있지 않으면, 경우에 사용할 수 없습니다는 **데이터 집합 프로젝트** 목록에 **속성** 창.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-separate-the-dataset-into-a-different-project"></a>다른 프로젝트에 데이터 집합을 구분 하려면  
  
1.  데이터 집합 (.xsd 파일)를 포함 하는 솔루션을 엽니다.  
  
    > [!NOTE]
    >  솔루션 넣을 데이터 집합 코드를 분리 하는 프로젝트를 포함 하지 않으면 프로젝트를 만들거나 기존 프로젝트를 솔루션에 추가 합니다.  
  
2.  형식화 된 데이터 집합 파일 (.xsd 파일)을 두 번 클릭 **솔루션 탐색기** 에서 데이터 집합을 열려는 **데이터 집합 디자이너**합니다.  
  
3.  빈 영역을 선택 된 **데이터 집합 디자이너**합니다.  
  
4.  에 **속성** 창을 찾습니다는 **데이터 집합 프로젝트** 노드.  
  
5.  에 **데이터 집합 프로젝트** 목록에서 데이터 집합 코드를 생성 하려면 프로젝트의 이름을 선택 합니다.  
  
     데이터 집합 코드를 생성할 프로젝트를 선택한 후는 **데이터 집합 파일** 속성은 기본 파일 이름으로 채워집니다. 필요한 경우이 이름을 변경할 수 있습니다. 또한 특정 디렉터리에 데이터 집합 코드를 생성 하려는 경우 설정할 수 있습니다는 **프로젝트 폴더** 속성 폴더의 이름입니다.  
  
    > [!NOTE]
    >  데이터 집합 및 TableAdapters를 분리할 때는 (설정 하 여는 **데이터 집합 프로젝트** 속성), 프로젝트의 기존 부분 데이터 집합 클래스가 자동으로 이동할 수 없습니다. 기존 부분 데이터 집합 클래스는 데이터 집합 프로젝트에 수동으로 이동 해야 합니다.  
  
6.  데이터 집합을 저장 합니다.  
  
     데이터 집합 코드에서 선택한 프로젝트에 생성 됩니다는 **데이터 집합 프로젝트** 속성 및 **TableAdapter** 현재 프로젝트에는 코드가 생성 됩니다.  
  
기본적으로 데이터 집합 및 TableAdapter 코드를 분리 한 후 결과는 각 프로젝트에 개별 클래스 파일이 합니다. 원래 프로젝트 파일에 TableAdapter 코드가 들어 있는 명명 된 DatasetName.Designer.vb (또는 DatasetName.Designer.cs). 에 지정 된 프로젝트는 **데이터 집합 프로젝트** 속성 파일에는 데이터 집합 코드를 포함 하 라는 DatasetName.DataSet.Designer.vb (또는 DatasetName.DataSet.Designer.cs).  
  
> [!NOTE]
>  생성 된 클래스 파일을 보려면 데이터 집합 또는 TableAdapter 프로젝트를 선택 합니다. 그런 다음 **솔루션 탐색기**선택, **모든 파일 표시**합니다.  
  
## <a name="see-also"></a>참고 항목
[N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)   
[연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)   
[계층적 업데이트](../data-tools/hierarchical-update.md)   
[Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)   
[ADO.NET](/dotnet/framework/data/adonet/index)
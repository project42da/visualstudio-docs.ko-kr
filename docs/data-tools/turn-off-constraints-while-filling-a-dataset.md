---
title: "데이터 집합을 채우는 동안 제약 조건을 해제할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 88c8687511dd600802cc7c6ecdc12f0827fd7f6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>데이터 집합을 채우는 동안 제약 조건 해제
제약 조건 (외래 키 제약 조건) 등을 포함 하는 데이터 집합, 데이터 집합에 대해 수행 하는 작업 순서와 관련 된 오류를 발생 시킬 수 있습니다. 부모 레코드가 제약 조건을 위반 하 고 오류가 발생할 수 예를 들어 관련 로드 하기 전에 자식 레코드를 로드 합니다. 자식 레코드를 로드 하는 즉시 제약 조건 관련된 부모 레코드에 대 한 확인 하 고 오류를 발생 시킵니다.  
  
 임시 제약 조건 일시 중단을 허용 하는 메커니즘이 있는 경우 자식 테이블에 레코드를 로드 하려고 할 때마다 오류가 발생 합니다. 다른 데이터 집합의 모든 제약 조건을 일시 중단 방법은 <xref:System.Data.DataRow.BeginEdit%2A>, 및 <xref:System.Data.DataRow.EndEdit%2A> 속성입니다.  
  
> [!NOTE]
>  유효성 검사 이벤트 (예를 들어 <xref:System.Data.DataTable.ColumnChanging> 및<xref:System.Data.DataTable.RowChanging>) 제약 조건을 해제 하는 경우 발생 하지 것입니다.  
  
### <a name="to-suspend-update-constraints-programmatically"></a>프로그래밍 방식으로 업데이트 제약 조건을 일시 중지 하려면  
  
-   다음 예제에는 데이터 집합에서 제약 조건 검사를 일시적으로 해제 하는 방법을 보여 줍니다.  
  
     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]  
  
### <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>데이터 집합 디자이너를 사용 하 여 업데이트 제약 조건을 일시 중지 하려면  
  
1.  데이터 집합을 열고는 **데이터 집합 디자이너**합니다. 자세한 내용은 참조 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.  
  
2.  에 **속성** 창에서 설정 된 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성을 `false`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Tableadapter를 사용 하 여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [데이터 집합에서의 관계](../data-tools/relationships-in-datasets.md)
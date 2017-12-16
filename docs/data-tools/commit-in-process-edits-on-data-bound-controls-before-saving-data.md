---
title: "데이터를 저장 하기 전에 데이터 바인딩된 컨트롤에서 in-process 편집 커밋 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- commiting edited records
- data-bound controls, in-process edits
- DataBinding class, commiting edited records
- hierarchical update, commiting edited records
- BindingSource class, commiting edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: d2b0ea1999c9742c04d1bb118d9a036ff2bed5ea
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>데이터를 저장 하기 전에 데이터 바인딩된 컨트롤에서 in-process 편집 커밋
데이터 바인딩된 컨트롤의 값을 편집할 때 사용자가 컨트롤에 바인딩되는 데이터 원본에 값이 업데이트를 적용 하려면 현재 레코드 탐색 해야 합니다. 항목을 끌면는 [데이터 소스 창](add-new-data-sources.md) 폼으로 끌어 놓으면 첫 번째 항목에는 코드를 생성 된 **저장** 단추 클릭 이벤트의는 <xref:System.Windows.Forms.BindingNavigator>합니다. 이 코드는 호출 된 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 의 메서드는 <xref:System.Windows.Forms.BindingSource>합니다. 따라서에 대 한 호출에서 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드가 첫 번째에 대해서만 생성 됩니다 <xref:System.Windows.Forms.BindingSource> 폼에 추가 된 합니다.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 호출 프로세스에 현재 편집 중인 데이터 바인딩된 컨트롤에 있는 모든 변경 내용을 커밋합니다. 따라서 데이터 바인딩된 컨트롤에 계속 포커스가 클릭는 **저장** 단추, 보류 중인 모든 편집 컨트롤 하면 실제 저장 전에 커밋된 한다는 점에서 (의 `TableAdapterManager.UpdateAll` 메서드).  
  
 사용자가 저장의 일부로 변경 내용을 커밋하지 않고 데이터를 저장 하려고 하는 경우에 자동으로 변경 내용을 적용 하려면 응용 프로그램을 구성할 수 있습니다 프로세스입니다.  
  
> [!NOTE]
>  디자이너는 추가 `BindingSource.EndEdit` 폼에 놓은 첫 번째 항목에 대해서만 코드입니다. 따라서 호출 하는 코드 줄을 추가 해야는 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드 각각에 대해 <xref:System.Windows.Forms.BindingSource> 폼에 있습니다. 호출 하는 코드 줄을 수동으로 추가할 수 있습니다는 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드 각각에 대해 <xref:System.Windows.Forms.BindingSource>합니다. 추가할 수 있습니다는 `EndEditOnAllBindingSources` 메서드를 폼 버전을 저장 하기 전에 호출 됩니다.  
  
 다음 코드에서는 [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/) 모두 반복 하는 쿼리 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 호출은 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드 각각에 대해 <xref:System.Windows.Forms.BindingSource> 폼에 있습니다.  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>폼에 모든 BindingSource 구성 요소에 대 한 EndEdit를 호출 하려면  
  
1.  다음 코드를 포함 하는 폼에 추가 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.vb)]  
  
2.  폼의 데이터를 저장 하는 호출 바로 앞의 코드의 다음 줄 추가 (의 `TableAdapterManager.UpdateAll()` 메서드):  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [계층적 업데이트](../data-tools/hierarchical-update.md)
---
title: "샘플 Excel 확장: ActionFilter 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 11
ms.author: douge
manager: douge
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5ab78b6b8eaa8156ed2c8a807b1d8a80e75afa84
ms.openlocfilehash: dc4805133aef7247e25ac4de123de084d5918304
ms.lasthandoff: 04/04/2017

---
# <a name="sample-excel-extension-actionfilter-class"></a>샘플 Excel 확장: ActionFilter 클래스
이 내부 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 클래스를 확장하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 요소에 대한 테스트 작업용 필터를 나타냅니다.  
  
## <a name="simple-properties"></a>단순 속성  
 개발자는 이러한 읽기 전용 속성을 통해 코딩된 UI 테스트 프레임워크에서 이 테스트 작업 필터를 실행할 방법을 지정할 수 있습니다. 예를 들어 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 속성은 작업 필터의 이름을 제공합니다. 작업 필터의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, 이 테스트 작업 필터에 의해 필터링되는 테스트 작업의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 이름을 가져오는 다른 속성도 있습니다. 그리고 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A>을 수행할지와, 테스트 작업이 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>인지 여부를 나타내는 속성도 있습니다.  
  
## <a name="processrule-method"></a>ProcessRule 메서드  
 이 메서드는 코딩된 UI 테스트 프레임워크에서 호출되며, 제공된 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>에 대해 필터를 실행합니다. 이 특정 재정의는 스택의 다음 작업에서 키 입력을 셀로 보낼 경우 해당 셀의 마우스 선택 작업을 제거합니다. 그런 다음 `false`를 반환합니다.  
  
## <a name="private-methods"></a>Private 메서드  
 `IsLeftClick` 메서드는 제공된 작업이 마우스 왼쪽 클릭을 나타내는지지를 확인합니다. `AreActionsOnSameExcelCell` 메서드는 제공된 두 작업이 Excel의 같은 셀에서 실행되는지를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)


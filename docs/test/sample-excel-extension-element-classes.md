---
title: "샘플 Excel 확장: 요소 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7c251098-00aa-49cf-9e37-5717c0c6b3f1
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "mlearned"
manager: "douge"
---
# 샘플 Excel 확장: 요소 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 확장은 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>에서 파생된 클래스를 사용하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]의 Worksheet 컨트롤 및 Cell 컨트롤을 나타냅니다.  
  
 이 확장의 기본 요소는 `ExcelElement`입니다.  `ExcelWorksheetElement` 클래스와 `ExcelCellElement` 클래스는 이 요소에서 상속됩니다.  
  
## Element 및 ElementInformation 클래스  
 `Element` 는 Excel 확장의 모든 사용자 인터페이스 요소에 대한 기본 클래스로, <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> 클래스에서 상속됩니다.  `ElementInformation`은 샘플의 요소 정보 클래스에 대한 기본 클래스이며 멤버가 없습니다.  
  
#### 단순 속성 및 메서드  
 이러한 멤버는 `Name` 속성 값이나 `ClassName` 속성 값과 같은 단순 값을 반환하며, 해당 코드는 명확하고 읽기 쉽습니다.  일부 값은 뒷부분에 설명된 `Utility` 클래스를 사용하여 반환됩니다.  다른 멤버는 이 샘플 확장과 관련이 없으므로 `null`을 반환합니다.  <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> 속성과 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.CacheProperties%2A> 메서드라는 두 멤버는 다른 멤버보다 유용합니다.  
  
#### QueryId 속성  
 이 속성은 재생 중 컨트롤을 고유하게 식별하는 속성의 이름\-값 쌍으로 구성된 조건을 반환합니다.  개발자는 파생된 각 컨트롤 클래스에 대해 프레임워크에서 UI의 컨트롤을 찾는 데 사용할 수 있는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement> 개체를 반환하도록 이 속성을 재정의해야 합니다.  
  
#### CacheProperties 메서드  
 이 메서드는 기록 프로세스 중에 요소가 중요한 속성의 스냅숏을 저장하도록 지정하기 위해 테스트 프레임워크에서 호출됩니다.  이 메서드는 실제 UI 컨트롤이 화면에서 더 이상 표시되지 않는 경우에도 속성을 사용할 수 있도록 유지합니다.  
  
## WorksheetElement 및 WorksheetInformation 클래스  
 `WorksheetElement`  클래스는 테스트 프레임워크에서 Excel 워크시트를 나타내며, 기본 클래스 `Element`에서 상속됩니다.  <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ClassName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ControlTypeName%2A> 및 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.Name%2A>라는 세 개의 속성은 Excel 워크시트 개체에 대한 특정 정보를 제공하도록 재정의됩니다.  
  
 이 클래스는 <xref:System.Runtime.InteropServices.ComVisibleAttribute>도 적용되므로 COM에 표시됩니다.  
  
 `WorksheetInformation`  클래스는 Excel 워크시트에 대한 정보를 나타냅니다.  이 클래스에는 멤버가 `SheetName` 속성 하나만 있으며 이 샘플에는 이 속성으로 충분합니다.  
  
## CellElement 및 CellInformation 클래스  
 `CellElement`  클래스는 Excel 셀을 나타내며, `Element` 기본 클래스에서 상속됩니다.  유일하게 재정의된 멤버는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> 속성이며, 이 속성은 `RowIndex` 및 `ColumnIndex` 속성을 사용하여 셀을 식별하는 데 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement>를 반환합니다.  
  
## Utilities 및 ExcelUtilities 클래스  
 내부 `ExcelUtilities` 클래스는 기술 이름과 같은 몇몇 상수 값과 제공된 창 핸들이 Excel 워크시트를 나타내는지 여부를 확인하는 메서드를 제공합니다.  
  
 `Utilities`  클래스에는 UI에 대한 다양한 정보를 반환하는 도우미 메서드가 있습니다.  일부 메서드는 **USER32.DLL** 및 **OLEACC.DLL**과 같은 외부 시스템 DLL을 직접 호출하여 UI에서 창 핸들을 가져옵니다**.**  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
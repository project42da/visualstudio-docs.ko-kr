---
title: "서버에 있는 문서의 데이터에 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], accessing on server
- data access [Office development in Visual Studio]
ms.assetid: 14a42e96-ed2f-48a1-a0c0-e19f9eba4956
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d81c8b10f5ace634cc58bd3135af9b2e69f1c519
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-data-in-documents-on-the-server"></a>서버에 있는 문서의 데이터 액세스
  Microsoft Office Word 또는 Microsoft Office Excel의 개체 모델을 사용 하지 않고도 문서 수준 사용자 지정에서 데이터에 대해 프로그래밍할 수 있습니다. 즉, 단어를 사용 하지 않은 서버에 문서에 포함 된 데이터에 액세스할 수 있습니다 또는 Excel이 설치 되어 있습니다. 예를 들어 서버에서 코드 (예를 들어,는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지) 문서에서 데이터를 사용자 지정 하 고 최종 사용자에 게 사용자 지정된 문서를 보낼 수 있습니다. 최종 사용자가 문서를 열면 솔루션 어셈블리에 데이터 바인딩 코드를 문서에 사용자 지정된 된 데이터를 바인딩합니다. 문서에서 데이터는 사용자 인터페이스에서 분리 되어 있으므로 이러한 작업이 가능 합니다. 자세한 내용은 참조 [문서 수준 사용자 지정의 캐시 된 데이터](../vsto/cached-data-in-document-level-customizations.md)합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="caching-data-for-use-on-a-server"></a>서버에서 사용할 데이터 캐싱  
 문서에서 데이터 개체를 캐시 하려면으로 표시는 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 사용 하 여 또는 디자인 타임에 특성의 `StartCaching` 메서드에서 런타임에 호스트 항목의 합니다. 문서에서 데이터 개체를 캐시 하는 경우는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 문서에 저장 하는 XML 문자열에는 개체를 serialize 합니다. 개체 캐싱 적합 하도록 할 특정 요구 사항을 충족 해야 합니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.  
  
 서버 쪽 코드는 데이터 캐시의 모든 데이터 개체를 조작할 수 있습니다. 캐시 된 데이터 인스턴스에 바인딩된 컨트롤을 데이터에 적용 된 모든 서버 쪽 변경 내용은 표시 되도록 자동으로 클라이언트에서 문서를 열 때 사용자 인터페이스와 동기화 됩니다.  
  
## <a name="accessing-data-in-the-cache"></a>캐시에 데이터 액세스  
 예를 들어 콘솔 응용 프로그램, Windows Forms 응용 프로그램 또는 웹 페이지에서 사무실 외부에서 응용 프로그램에서 캐시의 데이터에 액세스할 수 있습니다. 캐시 된 데이터에 액세스 하는 응용 프로그램에는 완전 신뢰에 있어야 합니다. 부분 신뢰 하는 웹 응용 프로그램 삽입, 검색, 하거나 Office 문서에서 캐시 된 데이터를 변경할 수 없습니다.  
  
 데이터 캐시에 의해 노출 되는 컬렉션의 계층 구조를 통해 액세스할 수는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 의 속성은 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스:  
  
-   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성에서 반환 된 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>, 문서 수준 사용자 지정의 캐시 된 데이터의 모든 포함 하는 합니다.  
  
-   각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData> 하나 이상 포함 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 개체입니다. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 단일 클래스 내에 정의 된 캐시 된 데이터 개체를 모두 포함 합니다.  
  
-   각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 하나 이상 포함 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 개체입니다. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 단일 캐시 된 데이터 개체를 나타냅니다.  
  
 다음 코드 예제에서는 캐시 된 문자열에 액세스 하는 방법을 보여 줍니다.는 `Sheet1` 는 Excel 통합 문서 프로젝트의 클래스. 이 예제는 제공 된 큰 예제의 일부는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드.  
  
 [!code-csharp[Trin_ServerDocument#12](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#12)]
 [!code-vb[Trin_ServerDocument#12](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#12)]  
  
## <a name="modifying-data-in-the-cache"></a>캐시에 데이터 수정  
 캐시 된 데이터 개체를 수정 하려면 일반적으로 다음 단계를 수행 합니다.  
  
1.  개체의 새 인스턴스를 캐시 된 개체의 XML 표현을 deserialize 됩니다. 사용 하 여 XML에 액세스할 수 있습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 의 속성은 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 캐시 된 데이터 개체를 나타내는입니다.  
  
2.  이 복사본을 변경 합니다.  
  
3.  다음 옵션 중 하나를 사용 하 여 데이터 캐시에 다시 변경된 된 개체를 serialize 합니다.  
  
    -   사용 하 여 변경 내용을 자동으로 serialize 하려는 경우는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드. 이 방법은 사용 하 여는 **DiffGram** 직렬화 하는 작업에 대 한 형식 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 데이터 캐시에 데이터 집합 개체를 입력 합니다. **DiffGram** 형식을 사용 하면 오프 라인 문서의 데이터 캐시에서 변경 내용이 서버에 올바르게 전달 됩니다.  
  
    -   캐시 된 데이터에 대 한 변경에 대 한 고유한 직렬화를 수행 하려는 경우를 작성할 수 있습니다에 직접는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 속성입니다. 지정 된 **DiffGram** 서식을 사용 하는 경우는 <xref:System.Data.Common.DataAdapter> 데이터에 적용 된 변경 내용과 데이터베이스를 업데이트 하는 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 형식화 된 데이터 집합 또는 합니다. 그렇지 않은 경우는 <xref:System.Data.Common.DataAdapter> 기존 행을 수정 하는 대신 새 행을 추가 하 여 데이터베이스를 업데이트 합니다.  
  
### <a name="modifying-data-without-deserializing-the-current-value"></a>현재 값을 역직렬화 하지 않고 데이터를 수정 합니다.  
 경우에 따라 현재 값을 역직렬화 하지 않고 캐시 된 개체의 값을 수정 하는 것이 좋습니다. 예를 들어 하면 문자열 또는 정수와 같은 단순 형식을 가진 개체의 값을 변경 하는 경우 또는 캐시 된 초기화 하는 경우 <xref:System.Data.DataSet> 문서에 서버입니다. 이러한 경우에 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드 없이 캐시 된 개체의 현재 값을 역직렬화 합니다.  
  
 캐시 된 문자열의 값을 변경 하는 방법은 다음 코드 예제는 `Sheet1` 는 Excel 통합 문서 프로젝트의 클래스. 이 예제는 제공 된 큰 예제의 일부는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드.  
  
 [!code-csharp[Trin_ServerDocument#11](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#11)]  
  
### <a name="modifying-null-values-in-the-data-cache"></a>데이터 캐시에서 Null 값을 수정  
 데이터 캐시 값을 가진 개체를 저장 하지 않는 **null** 문서를 저장 하 고 종료 하는 경우. 이 제한 사항은 다음과 같은 결과가 캐시 된 데이터를 수정 하는 경우:  
  
-   값에 데이터 캐시의 모든 개체를 설정 하는 경우 **null**, 데이터 캐시의 개체를 모두 자동으로로 설정 됩니다 **null** 문서를 열 때 전체 데이터 캐시를 지울 수는 시점과 문서를 저장 하 고 종료 합니다. 즉, 모든 캐시 된 개체에서에서 제거할 데이터 캐시 및 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 컬렉션이 비어 있게 됩니다.  
  
-   사용 하 여 솔루션을 작성 하는 경우 **null** 데이터 캐시의 개체를 사용 하 여 이러한 개체를 초기화 하려면는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 문서 하기 전에 클래스를 처음으로 연 경우 모든 개체의 초기화를 확인 해야 데이터 캐시 합니다. 일부 개체를 초기화 하는 경우 모든 개체가 설정 됩니다 **null** 때 문서를 열 및 문서를 저장 하 고 닫을 때 전체 데이터 캐시가 지워집니다.  
  
## <a name="accessing-typed-datasets-in-the-cache"></a>형식화 된 데이터 집합 캐시에 액세스  
 Office 솔루션에서와 같은 Windows Forms 응용 프로그램 사무실 외부에서 응용 프로그램에서 형식화 된 데이터 집합의 데이터에 액세스 하려는 경우 또는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 프로젝트를 둘 다에서 참조 되는 별도 어셈블리에서 형식화 된 데이터 집합을 정의 해야 프로젝트입니다. 사용 하 여 형식화 된 데이터 집합 각 프로젝트에 추가 하는 경우는 **데이터 소스 구성 마법사** 또는 **데이터 집합 디자이너**,.NET Framework는 서로 다른 형식으로 두 프로젝트의 형식화 된 데이터 집합을 처리 합니다 . 형식화 된 데이터 집합 만들기에 대 한 자세한 내용은 참조 [만들기 및 Visual Studio에서 데이터 집합을 구성](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)   
 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md)  
  
  
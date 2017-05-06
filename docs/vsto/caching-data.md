---
title: "데이터 캐싱"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터[Visual Studio에서 Office 개발], 캐싱"
  - "데이터 캐싱[Visual Studio에서 Office 개발]"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 데이터 캐싱 정보"
ms.assetid: 6f34251e-7d31-4f2b-ac17-42fd2837c626
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# 데이터 캐싱
  Microsoft Office Word나 Microsoft Office Excel을 열지 않고도 오프라인으로 데이터에 액세스할 수 있도록 문서 수준 사용자 지정의 데이터 개체를 캐시할 수 있습니다.  개체를 캐시하려면 개체의 데이터 형식이 특정 요구 사항을 충족해야 합니다.  <xref:System.String>, <xref:System.Data.DataSet> 및 <xref:System.Data.DataTable>을 비롯하여 .NET Framework의 많은 공통 데이터 형식은 이러한 요구 사항을 충족합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 데이터 캐시에 개체를 추가하는 방법은 다음 두 가지가 있습니다.  
  
-   솔루션이 빌드될 때 데이터 캐시에 개체를 추가하려면 개체 선언에 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 적용합니다.  자세한 내용은 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)을 참조하십시오.  
  
-   런타임에 프로그래밍 방식으로 데이터 캐시에 개체를 추가하려면 `ThisDocument` 또는 `ThisWorkbook` 클래스와 같은 호스트 항목의 `StartCaching` 메서드를 사용합니다.  자세한 내용은 [방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)을 참조하십시오.  
  
 데이터 캐시에 개체를 추가한 후에는 Word 또는 Excel을 시작하지 않고도 캐시된 데이터에 액세스하고 이를 수정할 수 있습니다.  자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하십시오.  
  
## 데이터 개체를 캐시하기 위한 요구 사항  
 솔루션의 데이터 개체를 캐시하려면 개체가 이러한 요구 사항을 충족해야 합니다.  
  
-   `ThisDocument` 또는 `ThisWorkbook` 클래스와 같은 호스트 항목의 읽기\/쓰기 공용 필드 또는 속성이어야 합니다.  
  
-   매개 변수가 있는 속성 또는 인덱서가 아니어야 합니다.  
  
 또한 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 데이터 개체를 serialize할 수 있어야 합니다. 즉, 개체의 형식에 다음과 같은 특징이 있어야 합니다.  
  
-   공용 형식이어야 합니다.  
  
-   매개 변수가 없는 공용 생성자가 있어야 합니다.  
  
-   추가적인 보안 권한을 요구하는 실행 코드가 아니어야 합니다.  
  
-   읽기\/쓰기 공용 속성만 노출해야 합니다. 기타 속성은 무시됩니다.  
  
-   다차원 배열을 노출하지 않아야 합니다. 중첩 배열은 허용됩니다.  
  
-   속성 및 필드에서 인터페이스를 반환하지 않아야 합니다.  
  
-   컬렉션인 경우 <xref:System.Collections.IDictionary>를 구현하지 않아야 합니다.  
  
 데이터 개체를 캐시하면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 개체를 문서의 *사용자 지정 XML 부분*에 저장된 XML 문자열로 serialize합니다.  자세한 내용은 [사용자 지정 XML 부분 개요](../vsto/custom-xml-parts-overview.md)을 참조하십시오.  
  
## 캐시된 데이터 크기 제한  
 문서의 데이터 캐시에 추가할 수 있는 데이터의 총 크기와 데이터 캐시의 개별 개체 크기에는 몇 가지 제한이 있습니다.  이 제한을 초과하면 데이터를 데이터 캐시에 저장할 경우 응용 프로그램이 예기치 않게 닫힐 수 있습니다.  
  
 이러한 제한을 피하려면 다음 지침을 따르십시오.  
  
-   10MB보다 큰 개체는 데이터 캐시에 추가하지 않습니다.  
  
-   총 크기가 100MB보다 큰 데이터는 단일 문서의 데이터 캐시에 추가하지 않습니다.  
  
 이러한 값은 대략적인 값입니다.  정확한 제한 값은 사용 가능한 RAM과 실행되는 프로세스 수를 비롯한 여러 가지 요소에 따라 달라집니다.  
  
## 캐시된 개체의 동작 제어  
 캐시된 개체의 동작을 좀더 세밀하게 제어하기 위해 캐시된 개체 형식에서 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> 인터페이스를 구현할 수 있습니다.  예를 들어, 개체가 변경되었을 때 이를 사용자에게 알리는 방식을 제어하려는 경우 이 인터페이스를 구현합니다.  <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>을 구현하는 방법을 보여 주는 코드 예제는 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Excel Dynamic Controls 샘플과 Word Dynamic Controls 샘플에서 `ControlCollection` 클래스를 참조하십시오.  
  
## 암호로 보호된 문서의 캐시된 데이터에 대한 변경 내용 유지  
 암호로 보호된 문서에서 데이터 개체를 캐시하면 캐시된 데이터에 대한 변경 내용이 저장되지 않습니다.  두 개의 메서드를 재정의하여 캐시된 데이터에 대한 변경 내용을 저장할 수 있습니다.  이러한 메서드를 재정의하여 문서가 저장될 때 보호를 일시적으로 해제했다가 저장 작업이 완료된 후 보호를 다시 적용합니다.  
  
 자세한 내용은 [방법: 암호로 보호된 문서의 데이터 캐시](../vsto/how-to-cache-data-in-a-password-protected-document.md)을 참조하십시오.  
  
## 데이터 캐시에 Null 값을 추가할 때 데이터 손실 방지  
 데이터 캐시에 개체를 추가하는 경우 문서가 저장되고 닫히기 전에 캐시된 개체가 모두 **null**이 아닌 값으로 초기화되어야 합니다.  문서가 저장되고 닫힐 때 값이 **null**인 캐시된 데이터가 있으면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 데이터 캐시에서 캐시된 모든 개체를 자동으로 제거합니다.  
  
 디자인 타임에 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 사용하여 데이터 캐시에 값이 **null**인 개체를 추가하는 경우 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 문서가 열리기 전에 캐시된 데이터 개체를 초기화할 수 있습니다.  이 방법은 최종 사용자가 문서를 열기 전에 Word 또는 Excel이 설치되어 있지 않은 서버에서 캐시된 데이터를 초기화하려는 경우에 유용합니다.  자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [방법: 암호로 보호된 문서의 데이터 캐시](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [연습: 캐시된 데이터 집합을 사용하여 마스터-세부 관계 만들기](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md)  
  
  
---
title: "FileName에 지정된 파일은 유효한 XML 파일이 아닙니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# FileName에 지정된 파일은 유효한 XML 파일이 아닙니다.
제공한 파일 이름이 유효한 XML 파일이 아닙니다. XML 문서의 허용된 구조와 내용을 지정하려면 DTD\(문서 종류 정의\), Microsoft XDR\(XML\-Data Reduced\) 스키마 또는 XSD\(XML 스키마 정의 언어\) 스키마를 사용하면 됩니다. XSD 스키마는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서 XML 문법을 지정하는 기본 방법입니다.  
  
> [!NOTE]
>  일부 이전 버전의 Visual Studio에서 **XML 디자이너**는 입력된 데이터 집합 및 XML 스키마용 디자이너입니다.**XML 디자이너**는 XML 스키마 파일을 만들고 편집하는 데 계속 사용할 수 있습니다. 그러나 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]에서 입력된 데이터 집합을 만들고 편집하는 디자이너는 **데이터 집합 디자이너**입니다. 자세한 내용은 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)을 참조하세요.  
  
### 이 오류를 해결하려면  
  
-   올바른 파일 이름을 제공했는지 확인합니다.  
  
-   확인하려는 XML 파일을 **XML 디자이너**로 로드하여 지정된 파일에 유효한 XML 파일이 포함되어 있는지 확인합니다.**XML** 메뉴에서 **XML 유효성 검사**를 클릭합니다.**작업 목록**에 오류가 표시됩니다.  
  
-   XML 파일에 연결된 XML 스키마가 있는 경우 요소가 정의된 구조에 표시되고 개별 요소의 콘텐츠가 스키마에서 지정된 선언된 데이터 형식에 맞는지 확인합니다.  
  
## 참고 항목  
 <xref:System.Xml>   
 [방법: 파일 경로의 구문 분석](../Topic/How%20to:%20Parse%20File%20Paths%20in%20Visual%20Basic.md)
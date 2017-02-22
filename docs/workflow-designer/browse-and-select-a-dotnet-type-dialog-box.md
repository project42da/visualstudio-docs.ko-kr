---
title: ".NET 유형 선택 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "09/02/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "TypeBrowser.UI"
  - "ActivityTypeResolver.UI"
ms.assetid: 864b60b6-a070-4e5c-aa5b-a25341b57ea6
caps.latest.revision: 13
caps.handback.revision: 13
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# .NET 유형 선택 대화 상자
**속성** 창, 대화 상자 또는 변수 디자이너와 같은 디자이너의 데이터 형식 목록에서 **형식 찾아보기…**를 선택하면 **.NET 유형 선택** 대화 상자가 나타납니다\(약칭 "형식 브라우저"\).이 대화 상자의 어셈블리 및 프로젝트 트리 뷰에서 형식을 선택할 수 있습니다.  
  
 이 대화 상자는 다음을 비롯한 여러 가지 사용자 시나리오에서 사용됩니다.  
  
-   변수 또는 인수의 형식을 설정할 때  
  
-   제네릭 동작의 형식을 선택할 때  
  
-   <xref:System.Activities.Statements.TryCatch> 활동에 catch를 추가할 때  
  
> [!NOTE]
>  형식 브라우저는 Visual Basic 가변 배열 형식을 표시할 수 있지만 다차원 배열 형식을 표시할 수 없습니다.자세한 내용은 [가변 배열](http://go.microsoft.com/fwlink/?LinkId=195226) 및 [다차원 배열](http://go.microsoft.com/fwlink/?LinkId=195227)을 참조하십시오.  
  
## 형식 브라우저에서 값 또는 참조 형식 선택  
  
#### 형식 브라우저에서 값 또는 참조 형식을 선택하려면  
  
1.  **형식 이름** 상자에 사용할 형식 이름을 입력합니다.  
  
2.  다음 작업 중 하나를 수행합니다.  
  
    -   사용할 형식 이름이 **형식 이름** 상자의 트리에 표시되면 해당 형식을 두 번 클릭합니다.  
  
    -   사용할 형식을 고유하게 식별하기에 충분한 수의 문자를 **형식 이름** 상자에 입력한 다음 Enter를 눌러 해당 형식을 선택합니다.  
  
#### 형식 브라우저에서 제네릭 형식을 선택하려면  
  
1.  **형식 이름** 상자에 사용할 형식 이름을 입력합니다.  
  
2.  사용할 형식 이름이 **형식 이름** 상자의 트리에 표시된 다음 해당 형식을 클릭하여 선택하면 드롭다운 상자가 나타납니다.  
  
     드롭다운 상자에서 제네릭을 닫는 데 사용할 형식을 선택한 다음 **확인**을 클릭합니다.  
  
## 형식 브라우저에 표시된 형식  
 형식 브라우저에 표시되는 형식은 형식 브라우저의 시작 방식에 따라 달라질 수 있습니다.**vs2010** 내의 워크플로 프로젝트에서 형식 브라우저를 시작한 경우, 기본적으로 참조한 어셈블리 및 참조한 프로젝트의 형식이 모두 표시됩니다.**vs2010** 프로젝트 시스템 외부\(예: 다시 호스팅된 워크플로 응용 프로그램이나 독립형 워크플로 파일\)에서 형식 브라우저를 시작한 경우에는 기본적으로 AppDomain에 로드된 모든 어셈블리의 형식이 표시됩니다.  
  
 활동 디자이너 개발자는 형식 브라우저의 형식을 필터링할 수 있습니다.특정 활동에서 형식의 하위 집합만 표시되는 경우가 있습니다.예를 들어 <xref:System.Activities.Statements.TryCatch> 활동의 경우 <xref:System.Exception>에서 파생된 형식만 형식 브라우저에 표시됩니다.  
  
## 형식 브라우저에서 검색 결과 필터링  
 일치하는 항목을 찾기 위해 문자를 많이 입력할수록 **형식 이름** 상자의 형식 목록이 짧아집니다.필터링된 목록에는 정규화된 이름 또는 약식 이름이 입력한 문자열로 시작되는 형식만 표시됩니다.  
  
 예를 들면 다음과 같습니다.  
  
1.  입력값 **Operation**은 <xref:System.OperationCanceledException>과 일치하지만 <xref:System.InvalidOperationException>과는 일치하지 않습니다.<xref:System.InvalidOperationException>을 찾으려면 System.I 또는 Invalid를 입력해야 합니다.  
  
2.  입력값 **Generic**은 <xref:System.GenericUriParser>와 일치하지만 <xref:System.Collections.Generic> 네임스페이스의 형식과는 일치하지 않습니다.<xref:System.Collections.Generic> 네임스페이스의 형식을 검색하려면 해당 네임스페이스의 정규화된 이름을 입력해야 합니다.  
  
## 형식 브라우저 대화 상자를 사용하여 서비스 계약 선택  
 서비스 계약 형식을 선택할 때 형식 브라우저는 <xref:System.ServiceModel.ServiceContractAttribute> 특성이 있는 형식만 보여줍니다.  
  
## 참고 항목  
 [활동 디자이너 사용](../workflow-designer/using-the-activity-designers.md)
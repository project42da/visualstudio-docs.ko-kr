---
title: "모델링 프로젝트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 개체를 구현 하는 자동화 [Visual Studio SDK]"
  - "프로젝트 모델을 자동화"
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 모델링 프로젝트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 표준 프로젝트 개체를 구현 하는 것에 대 한 자동화를 제공 하는 다음 단계: 해당 <xref:EnvDTE.Projects> 및 `ProjectItems` 컬렉션입니다. the `Project` and <xref:EnvDTE.ProjectItem> objects; 한 나머지 개체를 구현 하는 고유 합니다.  이러한 표준 개체 Dteinternal.h 파일에 정의 됩니다.  표준 개체의 구현 BscPrj 샘플에서 제공 됩니다.  왼쪽 \/ 오른쪽 눈에 띄는 직접 표준 프로젝트 개체를 만들려면 모델로 이러한 클래스를 사용할 수 있습니다 프로젝트 개체에서 다른 프로젝트 형식 사용 합니다.  
  
 자동화 소비자 호출할 수 하는 것으로 간주 <xref:EnvDTE.Solution>\("`<UniqueProjName>")` 및 <xref:EnvDTE.ProjectItems> \(`n`\)는 n 얻는 솔루션에서 특정 프로젝트에 대 한 인덱스 번호입니다.  이 자동화 호출을 수행 하면 호출 하는 환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> VSITEMID\_ROOT ItemID 매개 변수 및 VSHPROPID\_ExtObject VSHPROPID 매개 변수로 전달 하 여 적절 한 프로젝트 계층 구조에 있습니다.  `IVsHierarchy::GetProperty`반환는 `IDispatch` 의 핵심을 제공 하는 자동화 개체 포인터를 `Project` 인터페이스를 구현 합니다.  
  
 다음 구문은 `IVsHierarchy::GetProperty`.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`,  
  
 `VSHPROPID` `propid`,  
  
 `VARIANT` `*pvar`  
  
 `);`  
  
 프로젝트는 중첩 수용 및 컬렉션을 사용 하 여 프로젝트 항목의 그룹을 만들 수 있습니다.  계층 구조는 다음과 같이 나타납니다.  
  
```  
Projects  
  |– Project  
      |– ProjectItems (a collection of ProjectItem)  
          |– ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 중첩을 의미 하는 <xref:EnvDTE.ProjectItem> 개체가 될 수 있습니다 <xref:EnvDTE.ProjectItems> 동시에 컬렉션 때문에 `ProjectItems` 컬렉션에서 중첩된 객체가 포함 될 수 있습니다.  기본 프로젝트 샘플이 중첩을 보여 주지 않습니다.  구현 하는 `Project` 개체를 참가할 트리 모양의 구조에 전체 자동화 모델의 디자인을 나타냅니다.  
  
 프로젝트 자동화 다음 다이어그램에서의 경로 다음과 같습니다.  
  
 ![Visual Studio 프로젝트 개체](../../extensibility/internals/media/projectobjects.png "ProjectObjects")  
자동화 프로젝트  
  
 구현 하지 않는 경우는 `Project` 개체에서 환경 일반 계속 반환 `Project` 프로젝트 이름을 포함 하는 개체입니다.  
  
## 참고 항목  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>
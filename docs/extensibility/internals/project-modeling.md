---
title: "모델링 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d654669ad35ce77d840f4852ceb7a6605a8221be
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="project-modeling"></a>모델링 프로젝트
표준 프로젝트 개체를 구현 하는 프로젝트에 대 한 자동화를 제공 하는 다음 단계:는 <xref:EnvDTE.Projects> 및 `ProjectItems` 컬렉션; `Project` 및 <xref:EnvDTE.ProjectItem> 개체; 및 나머지 개체 구현에 고유 합니다. 이러한 표준 개체 Dteinternal.h 파일에 정의 됩니다. 표준 개체의 구현은 BscPrj 샘플에 제공 됩니다. 나란히 구분할 수 있도록 표준 프로젝트 개체를 직접 만드는를 모델으로 이러한 클래스를 사용할 수 있습니다 다른 프로젝트 형식에서 프로젝트 개체와 사용 합니다.  
  
 자동화 소비자를 호출 하려면 가정 <xref:EnvDTE.Solution>("`<UniqueProjName>")` 및 <xref:EnvDTE.ProjectItems> (`n`) 여기서 n은 솔루션의 특정 프로젝트 가져오기에 대 한 인덱스 번호입니다. 호출할 환경을 사용 하면이 자동화 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> VSITEMID_ROOT ItemID 매개 변수 및 VSHPROPID_ExtObject VSHPROPID 매개 변수로 전달 하는 적절 한 프로젝트 계층 구조에 있습니다. `IVsHierarchy::GetProperty`반환 된 `IDispatch` 핵심을 제공 하는 자동화 개체에 대 한 포인터 `Project` 인터페이스를 구현 합니다.  
  
 다음은 구문의 `IVsHierarchy::GetProperty`합니다.  
  
 `HRESULT GetProperty (`  
  
 `VSITEMID` `itemid`을 참조하십시오.  
  
 `VSHPROPID` `propid`을 참조하십시오.  
  
 `VARIANT` `*pvar`  
  
 `);`  
  
 프로젝트 중첩 수용 및 프로젝트 항목의 그룹을 만들 컬렉션을 사용 합니다. 계층 구조는 다음과 같습니다.  
  
```  
Projects  
  |- Project  
      |- ProjectItems (a collection of ProjectItem)  
          |- ProjectItem (single object) or ProjectItems (another collection)  
```  
  
 중첩 됨을 의미는 <xref:EnvDTE.ProjectItem> 개체 일 수 <xref:EnvDTE.ProjectItems> 동시에 컬렉션 때문에 `ProjectItems` 컬렉션에는 중첩 된 개체가 포함 될 수 있습니다. 기본 프로젝트 샘플이이 중첩을 보여 주지 않습니다. 구현 하 여는 `Project` 디자인 전반적인 자동화 모델의 특성을 지정 하는 트리와 같은 구조에 참여 하는 개체입니다.  
  
 프로젝트 자동화는 다음 다이어그램에 경로 따라갑니다.  
  
 ![Visual Studio 프로젝트 개체](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")  
프로젝트 자동화  
  
 구현 하지 않는 경우는 `Project` 개체 환경 제네릭 반환 됩니다 `Project` 프로젝트의 이름만 포함 하는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:EnvDTE.Projects>   
 <xref:EnvDTE.ProjectItem>   
 <xref:EnvDTE.ProjectItems>
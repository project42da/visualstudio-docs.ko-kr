---
title: "코드에 대 한 자동화를 제공합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CodeModel 개체"
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 코드에 대 한 자동화를 제공합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

자동화 모델에 대 한 코드를 작성 하지 않아도 됩니다.  환경 SDK 샘플 작업에 대 한 제공 하지 않습니다.  통찰력 코드 모델을 참조 하십시오 해당 <xref:EnvDTE.CodeModel> 개체입니다.  
  
 코드 모델을 구현 하 여 내부 데이터 구조를 결정 하는 모든 인터페이스를 구현 해야 합니다.  개체에서 파생 되어야 합니다는 `IDispatch` 클래스입니다.  
  
 확장 하 여, 개체 <xref:EnvDTE.CodeModel> 및 <xref:EnvDTE.FileCodeModel>, 사용할 수 있는 <xref:EnvDTE.Project> 한은 다음과 비슷합니다:  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 구현 하도록 선택할 수 있습니다 뿐만 아니라 `CodeModel` 또는 `FileCodeModel` 인터페이스에서 반환 하는 개체에를 `Project` 및 <xref:EnvDTE.ProjectItem> 개체입니다.  프로젝트 시스템에 대 한 적합이 인터페이스에서 모든 기능을 제공 합니다.  
  
 메서드 또는 속성에서 같은 기능을 추가 하려는 경우에 사용할 수 없습니다 표준에서 `CodeModel` 및 `FileCodeModel` 인터페이스를 표준에서 상속 사용자 인터페이스 만들기.  찾으려면 최종 사용자가 알 수 있도록 프로젝트 시스템을 문서화 해야 합니다.  표준 인터페이스를 반환 하지만 사용자를 호출할 수 있습니다의 `QueryInterface` 메서드 또는 존재를 알고 있는 경우 해당 인터페이스에 캐스팅 합니다.  
  
## 참고 항목  
 [자동화 모델 개요](../../extensibility/internals/automation-model-overview.md)
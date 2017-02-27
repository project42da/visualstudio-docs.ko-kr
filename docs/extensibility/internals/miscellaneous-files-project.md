---
title: "기타 파일 프로젝트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파일, 솔루션에 기존 파일 추가"
  - "기타 파일 프로젝트"
  - "솔루션 항목 폴더"
  - "파일, 기타 파일 프로젝트 열기"
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 기타 파일 프로젝트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE 사용자 프로젝트 항목을 열면 기타 파일 프로젝트에 솔루션에서 모든 프로젝트 멤버가 아닌 항목을 할당 합니다.  
  
 프로젝트 사용자 프로젝트 항목을 열 때 사용할 편집기를 사용 하는 결정 하는 중요 한 역할을 합니다.  프로젝트를 특정 파일을 프로젝트 고유 편집기 또는 표준 편집기를 사용 하 여 열을 디자인할 수 있습니다.  
  
 프로젝트 고유 편집기는 일반적으로 사용자가 특별 한 기술 하거나 특별 한 인터페이스는 프로젝트에서 사용 하는 필요 합니다.  자세한 내용은 [방법: 프로젝트에 특정 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)를 참조하십시오.  
  
 표준 편집기 모든 프로젝트에서 특정 확장명의 파일을 열 수 있습니다.  사용자 같은 일부 표준 편집기를 사용자 지정할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트에 대 한 텍스트 편집기가 공용 문자를 유지 하지만 여전히.  표준 편집기를 사용 하 여 만들는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드가 있습니다.  
  
 프로젝트 항목을 열 수 없는 프로젝트를 솔루션에서 응답 하는 경우 파일을 여는 기타 파일 프로젝트 라는 특별 한 프로젝트를 IDE를 제공 합니다.  
  
 이 특별 한 프로젝트를 여는 프로젝트의 컨텍스트 외부에 있는 파일을 제공합니다.  처리 중의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> 방법, 기타 파일 프로젝트 항상 응답의 매우 낮은 우선 순위를 합니다.  따라서, 기타 파일 파일을 열 수는 더 높은 우선 순위 프로젝트에 수확량 항상 프로젝트입니다.  
  
 기타 파일 프로젝트를 만들 때 사용자가 필요 하지 않습니다을  **새 프로젝트** 대화 상자.  또한 기타 파일 프로젝트 프로젝트 구성원 목록을 영구히 관리 하지 않습니다.  선택적 기능을 사용 하 여 각 사용자에 대해 가장 최근에 사용한 파일 목록을 기록 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>   
 [방법: 프로젝트에 특정 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)
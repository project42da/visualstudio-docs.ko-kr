---
title: "프로젝트 지 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 지 속성"
  - "프로젝트 [Visual Studio SDK], 지 속성"
ms.assetid: 42907bcf-4e27-46bd-a8cb-01c2ccd2bde5
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로젝트 지 속성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

주요 디자인 프로젝트에 대 한 유지가 됩니다.  대부분의 프로젝트 파일을 표시 하는 프로젝트 항목을 사용 합니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]또한 파일 기반 데이터는 프로젝트를 지원 합니다.  프로젝트 및 프로젝트 파일에서 소유 하 고 있는 파일 모두 유지 해야 합니다.  IDE 자체 또는 프로젝트 항목을 저장 하는 프로젝트에 지시 합니다.  
  
 프로젝트 템플릿은 프로젝트 공장에 전달 됩니다.  템플릿 초기화 요구 특정 프로젝트 형식에 따라 프로젝트 항목을 모두를 지원 해야 합니다.  이러한 템플릿은 프로젝트 파일 형식으로 저장 고 나중에 IDE에서 솔루션을 통해 관리 하는 수입니다.  자세한 내용은 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md) 및 [솔루션](../../extensibility/internals/solutions.md)을 참조하십시오.  
  
 프로젝트 항목 파일 기반 또는 파일 기반 일 수 있습니다.  
  
-   파일 기반 항목 로컬 이나 원격 일 수 있습니다.  원격 시스템에서 파일 자체를 유지 하는 반면 C\#에서 웹 프로젝트의 예를 들어, 연결 원격 시스템에서 파일을 로컬에서 유지 됩니다.  
  
-   항목 파일 기반 데이터베이스나 저장소에 항목을 저장할 수 있습니다.  
  
## 적용 모델  
 프로젝트 항목이 위치한를 결정 한 후 해당 커밋 모델을 선택 해야 합니다.  예를 들어, 로컬 파일은 파일 기반 모델의 각 프로젝트 자율적으로 저장할 수 있습니다.  저장소 모델에서 트랜잭션 하나에 여러 개의 항목을 저장할 수 있습니다.  자세한 내용은 [프로젝트 형식에 대 한 설계 결정 사항](../../extensibility/internals/project-type-design-decisions.md)를 참조하십시오.  
  
 프로젝트 파일 이름 확장명을 확인 하려면 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 구현 하 여 클라이언트 개체의 정보를 제공 하는 인터페이스는  **다른 이름으로 저장** 대화 상자\-, 채울 수는  **형식** 드롭다운 나열 및 관리의 초기 파일 이름 확장명.  
  
 IDE 호출을 `IPersistFileFormat` 인터페이스 프로젝트의 프로젝트 유지 되어야 함을 나타내려면 프로젝트에 항목을 적절 하 게 합니다.  따라서 개체는 파일, 서식의 모든 측면을 소유합니다.  여기에 개체의 형식 이름입니다.  
  
 항목이 파일에 없는 경우 `IPersistFileFormat` 여전히 어떻게 파일 기반이 아닌입니다 항목이 유지 됩니다.  프로젝트의.vbp 파일 같은 파일 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 또는.vcproj 파일에 대 한 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트, 유지 해야 수도 있습니다.  
  
 검사에 대 한 작업 저장 IDE 실행 문서 테이블 \(RDT\) 하 고 명령에 계층 구조를 통과 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> 인터페이스입니다.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.IsItemDirty%2A> 메서드 구현 된 항목이 수정 되었는지 여부를 확인 합니다.  항목이 있는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.SaveItem%2A> 수정 된 항목을 저장할 메서드를 구현 합니다.  
  
 메서드는 `IVsPersistHierarchyItem2` 인터페이스 항목을 다시 로드할 수 있습니다 여부 및 다시 로드 하는 항목 수 있습니다 경우 결정 하는 데 사용 됩니다.  또한, 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IgnoreItemFileChanges%2A> 항목은 변경 내용이 저장 되지 않고 삭제를 메서드를 구현할 수 있습니다.  
  
## 참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)
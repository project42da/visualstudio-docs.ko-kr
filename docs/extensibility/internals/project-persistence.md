---
title: "프로젝트 지 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- persistence, projects
- projects [Visual Studio SDK], persistance
ms.assetid: 42907bcf-4e27-46bd-a8cb-01c2ccd2bde5
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d77c307ec7b732ba727b7210b4f4eaacb44584aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="project-persistence"></a>프로젝트 지 속성
지 속성은 프로젝트에 대 한 중요 한 설계 고려 합니다. 대부분의 프로젝트 파일; 나타내는 프로젝트 항목 사용 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 도 데이터가 파일 기반이 아닌 된 프로젝트를 지원 합니다. 프로젝트 및 프로젝트 파일을 소유한 파일 모두 유지 해야 합니다. IDE 자체 또는 프로젝트 항목을 저장 하려면 프로젝트에 지시 합니다.  
  
 프로젝트에 대 한 서식 파일 프로젝트 팩터리로 전달 됩니다. 템플릿은 특정 프로젝트 형식이 요구 사항에 따라 모든 프로젝트 항목의 초기화를 지원 해야 합니다. 이러한 서식 파일 프로젝트 파일로 저장 및 나중에 솔루션을 통해 IDE에 의해 관리 되는 수 있습니다. 자세한 내용은 참조 [만들기 프로젝트 인스턴스 여를 사용 하 여 프로젝트 팩터리](../../extensibility/internals/creating-project-instances-by-using-project-factories.md) 및 [솔루션](../../extensibility/internals/solutions.md)합니다.  
  
 프로젝트 항목 파일 기반 또는 파일 기반 하나일 수 있습니다.  
  
-   로컬 또는 원격 파일 기반 항목 수 있습니다. C#에서 웹 프로젝트에서는 예를 들어 원격 시스템에 있는 파일에 대 한 연결 유지를 로컬로 파일 자체 원격 시스템에 유지 하는 반면 합니다.  
  
-   항목 파일 기반 데이터베이스 또는 저장소 항목을 저장할 수 있습니다.  
  
## <a name="commit-models"></a>모델을 커밋  
 에 프로젝트 항목이 있는 위치를 결정 한 후 적절 한 커밋 모델을 선택 해야 합니다. 예를 들어 로컬 파일에 파일 기반 모델에서 각 프로젝트를 저장 자치 적으로 작동 합니다. 저장소 모델의 한 트랜잭션에 여러 항목을 저장할 수 있습니다. 자세한 내용은 참조 [프로젝트 형식에 대 한 디자인 관련 결정](../../extensibility/internals/project-type-design-decisions.md)합니다.  
  
 프로젝트 파일 이름 확장명을 확인 하려면 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 인터페이스를 구현 하는 개체의 클라이언트를 사용 하도록 설정 하는 정보를 제공 하는 **다른 이름으로 저장** 대화 상자-즉,를 작성 하는 **파일 형식**  드롭 다운 나열 하 고 초기 파일 이름 확장명을 관리 합니다.  
  
 IDE 호출은 `IPersistFileFormat` 인터페이스를 프로젝트의 프로젝트를 유지 해야 함을 나타내는 프로젝트에 항목을 적절 하 게 합니다. 따라서 개체는 해당 파일 및 형식을의 모든 측면을 소유합니다. 여기에 개체의 형식 이름입니다.  
  
 항목은 파일, 되지 경우에서 `IPersistFileFormat` 는 여전히 어떻게 파일 기반이 아닌 항목 유지 됩니다. 프로젝트 파일에 대 한.vbp 파일과 같은 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vcproj 또는 프로젝트 파일에 대 한 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 도 프로젝트를 저장 해야 합니다.  
  
 에 대 한 작업을 저장 IDE 검사 하 여 실행 중인 문서 테이블 (RDT) 및 계층 구조에는에 명령을 전달는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> 인터페이스입니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.IsItemDirty%2A> 메서드 항목 수정 되었는지 여부를 결정 하기 위해 구현 됩니다. 항목에 있는 경우, 고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.SaveItem%2A> 메서드는 구현 하 여 수정 된 항목을 저장 합니다.  
  
 메서드는 `IVsPersistHierarchyItem2` 인터페이스는 항목을 다시 로드 될 수 있는지 여부를 및 다시 로드 하는 항목 일 수 있으면 확인 하는 데 사용 됩니다. 또한는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IgnoreItemFileChanges%2A> 인해 변경 된 항목에 내용이 저장 되지 않고 삭제 하도록 메서드를 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [프로젝트 팩터리를 사용하여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)
---
title: "사용자 지정 편집기에서 문서 데이터 및 문서를 볼 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - document data and document view
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7c7e24ed2db4538ab0fd38dbb85930452611f0ee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="document-data-and-document-view-in-custom-editors"></a>문서 데이터와 사용자 지정 편집기에서 문서 보기
사용자 지정 편집기 두 부분으로 이루어져: 문서 데이터 개체와 문서 뷰 개체입니다. 이름을 통해 알으로 문서 데이터 개체로 텍스트 데이터를 표시할 수를 나타내며 문서 뷰 개체 (또는 "view") 문서 데이터 개체로 표시 하는 하나 이상의 창.  
  
## <a name="document-data-object"></a>문서 데이터 개체  
 문서 데이터 개체에는 텍스트 버퍼의 텍스트 데이터 표현입니다. 문서 텍스트 및 기타 정보 저장, 처리 하는 문서 지 속성 및 해당 데이터의 여러 뷰를 사용 하도록 설정 하는 COM 개체 이므로 합니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 <xref:EnvDTE80.Window2.DocumentData%2A>및 [문서](../extensibility/internals/document-windows.md)합니다.  
  
 사용자 지정 편집기 및 디자이너를 사용 하도록 선택할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체 또는 고유한 사용자 지정 하는 버퍼입니다. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>표준 편집기에 대 한 포함 하는 간단한 모델을 따릅니다 여러 뷰를 지원 하며 여러 보기를 관리 하는 데 사용 되는 이벤트 인터페이스를 제공 합니다.  
  
## <a name="document-view-object"></a>문서 뷰 개체  
 코드 및 기타 텍스트를 표시 하는 창을 문서 라고 보기 또는 보기입니다. 편집기를 만들 때 텍스트는 하나의 창에 표시 되는 단일 뷰를 또는 여러 개 창에 표시 되는 텍스트를 여러 보기를 선택할 수 있습니다. 선택한 응용 프로그램에 따라 달라 집니다. 예를 들어-나란히 편집 필요한 경우에 여러 보기를 선택 합니다. 각 보기는 통합된 개발 환경에서의 (IDE) document 테이블 (RDT) 실행 항목으로 연결 됩니다. 프로젝트에 속하는 보기 창 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 개체입니다.  
  
 편집기에서 문서 데이터 개체의 여러 뷰를 지 원하는 경우 다음 문서 데이터 및 문서 보기 개체 구분 되어야 합니다. 그렇지 않으면 이러한 그룹화 할 수 있습니다. 자세한 내용은 참조 [여러 문서 보기를 지 원하는](../extensibility/supporting-multiple-document-views.md)합니다.  
  
 IDE에 실행 중인 문서 테이블의 각 항목에 대 한 항목 식별자 (ItemID)를 비교 하 여 (예: 문서를 포함 하는 솔루션을 닫으면) 이벤트에 대 한 뷰를 알립니다. 이 대 한 자세한 내용은 참조 하십시오. [실행 중인 문서 테이블](../extensibility/internals/running-document-table.md)합니다.  
  
 사용자 지정 편집기에 대 한 보기를 만드는 방법은 두 가지가 있습니다. 하나는 ActiveX 컨트롤 또는 문서 데이터 개체로 사용 하 여 창에서 보기 호스팅되는 내부 활성화 모델입니다. 두 번째는 보기에서 호스팅되는 포함 간단한 모델, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 창 명령을 처리 하기 위해 구현 됩니다. 바로 활성화 모델에 대 한 정보를 참조 하십시오. [내부 활성화](../extensibility/in-place-activation.md)합니다. 간단한 포함 모델에 대 한 정보를 참조 하십시오. [단순화 포함](../extensibility/simplified-embedding.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [포함 하는 간소화 된](../extensibility/simplified-embedding.md)   
 [방법: 뷰 문서 데이터를 연결 합니다.](../extensibility/how-to-attach-views-to-document-data.md)   
 [문서 잠금 소유자 관리](../extensibility/document-lock-holder-management.md)   
 [단일 및 다중 탭 뷰](../extensibility/single-and-multi-tab-views.md)   
 [표준 문서 저장](../extensibility/internals/saving-a-standard-document.md)   
 [지 속성 및 실행 중인 문서 테이블](../extensibility/internals/persistence-and-the-running-document-table.md)   
 [편집기 열리는 프로젝트의 파일 확인](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)   
 [편집기 팩터리](../extensibility/editor-factories.md)
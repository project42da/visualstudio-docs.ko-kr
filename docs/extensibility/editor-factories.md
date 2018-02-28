---
title: "편집기 팩터리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - editor factories
ms.assetid: cf4e8164-3546-441d-b465-e8a836ae7216
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e0fb464d3eb9d7b39b853593c9458fe800296321
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="editor-factories"></a>편집기 팩터리
편집기 팩터리 편집기 개체를 만들고 물리적 뷰 라고 하는 창 프레임에 저장 합니다. 문서 데이터와 편집기 및 디자이너를 만드는 데 필요한 문서 뷰 개체를 만듭니다. 편집기 팩터리 Visual Studio 코어 편집기 및 모든 표준 편집기를 만드는 데 필요 합니다. 사용자 지정 편집기 편집기 팩터리와 선택적으로 만들 수 있습니다.  
  
 구현 하 여 편집기 팩터리를 만들어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스입니다. 다음 예제에서는 구현 하는 방법을 보여 줍니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 편집기 팩터리를 만들어야 합니다.  
  
 [!code-vb[VSSDKEditorFactories#1](../extensibility/codesnippet/VisualBasic/editor-factories_1.vb)]
 [!code-csharp[VSSDKEditorFactories#1](../extensibility/codesnippet/CSharp/editor-factories_1.cs)]  
  
 편집기는 해당 편집기에서 처리 하는 파일 형식을 사용자가 처음으로 로드 됩니다. 특정 편집기 또는 기본 편집기를 열 수 있습니다. 기본 편집기를 선택 하는 경우 통합된 개발 환경 (IDE) 올바른 열 편집기를 결정 하 고 엽니다. 자세한 내용은 참조 [프로젝트의 파일을 열 편집기 결정](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)합니다.  
  
## <a name="registering-editor-factories"></a>편집기 팩터리를 등록 하는 중  
 사용자가 만든 편집기를 사용 하려면 먼저에 대 한 정보를 처리할 수 있는 파일 확장명을 포함 하 여 먼저 등록 해야 합니다.  
  
 관리 되는 코드를 VSPackage를 작성 하는 경우 관리 되는 패키지 프레임 워크 MPF () 메서드를 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> VSPackage를 로드 한 후 편집기 팩터리를 등록할 수 있습니다. VSPackage는 비관리 코드에서 작성 된 경우 사용 하 여 편집기 팩터리를 등록 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors> 서비스입니다.  
  
### <a name="registering-an-editor-factory-by-using-managed-code"></a>관리 코드를 사용 하 여 편집기 팩터리를 등록 하는 중  
 VSPackage의의 편집기 팩터리를 등록 해야는 `Initialize` 메서드. 먼저 호출 `base.Initialize`, 한 다음 호출 <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> 각 편집기 팩터리의  
  
 관리 코드, 즉 한 편집기 팩터리 등록을 취소할 필요가 없습니다 VSPackage는 자동으로 처리 하기 때문에 있습니다. 또한 편집기 팩터리를 구현 하는 경우 <xref:System.IDisposable>, 등록 되어 있지 않은 경우 자동으로 삭제 됩니다.  
  
### <a name="registering-an-editor-factory-by-using-unmanaged-code"></a>비관리 코드를 사용 하 여 편집기 팩터리를 등록 하는 중  
 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 편집기 패키지를 사용 하 여 구현 된 `QueryService` 호출할 메서드를 `SVsRegisterEditors`합니다. 이 작업에 대 한 포인터를 반환 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>합니다. 호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> 메서드 구현에 전달 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스입니다. Mplement 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 별도 클래스에 있습니다.  
  
## <a name="the-editor-factory-registration-process"></a>편집기 팩터리 등록 프로세스  
 다음 프로세스는 Visual Studio 편집기 팩터리를 사용 하 여 편집기를 로드할 때 발생 합니다.  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 시스템 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>합니다.  
  
2.  이 메서드는 편집기 팩터리를 반환합니다. 그러나 Visual Studio 지연 프로젝트 시스템 편집기를 실제로 필요할 때까지 편집기의 패키지를 로드 합니다.  
  
3.  프로젝트 시스템에서 편집기를 필요한 경우 Visual Studio 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>, 문서 보기와 문서 데이터 개체를 반환 하는 특수 한 메서드입니다.  
  
4.  경우에 편집기 팩터리를 사용 하 여 Visual Studio에서 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 문서 데이터 개체와 문서 뷰 개체를 모두 반환, Visual Studio 다음 문서 창, 문서 보기 개체 배치 만들고를 실행 중인 문서에 항목 문서 데이터 개체에 대 한 테이블 (RDT) 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>   
 [문서 테이블 실행](../extensibility/internals/running-document-table.md)
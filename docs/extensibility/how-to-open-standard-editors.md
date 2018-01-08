---
title: "방법: 표준 편집기를 열어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], opening
- projects [Visual Studio SDK], opening standard editors
ms.assetid: d5ce10f9-047a-4b74-aa1d-295128898b89
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dcf36dc8f4ef818a84719bc534a09ecf30baf76f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-standard-editors"></a>방법: 표준 편집기 열기
표준 편집기를 열면 IDE 파일에 대 한 프로젝트 관련 편집기를 지정 하는 대신 지정 된 파일 형식에 대해 표준 편집기를 결정 하도록 할 수 있습니다.  
  
 구현 하는 다음 절차는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드. 프로젝트 파일을 표준 편집기에서 열립니다.  
  
### <a name="to-implement-the-openitem-method-with-a-standard-editor"></a>표준 편집기로 OpenItem 메서드를 구현 하려면  
  
1.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> (`RDT_EditLock`) 문서 데이터 개체 파일은 이미 열려 있는지 여부를 확인 하려면.  
  
2.  파일이 이미 열려 있으면 호출 하 여 파일을 resurface는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 값을 지정 하는 메서드를 `IDO_ActivateIfOpen` 에 대 한는 `grfIDO` 매개 변수입니다.  
  
     파일이 열려 문서 보다 호출 하는 프로젝트는 다른 프로젝트에서 소유 하는 경우 프로젝트는 다른 프로젝트에서 열려는 편집기가 된다는 경고가 표시 합니다. 다음 파일 창에 표시 됩니다.  
  
3.  실행 중인 문서 테이블에 없는 또는 문서가 열려 있지 않으면 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드 (`OSE_ChooseBestStdEditor`) 파일에 대 한 표준 편집기를 엽니다.  
  
     메서드를 호출 하는 경우 IDE는 다음과 같은 작업을 수행 합니다.  
  
    1.  IDE 편집기 검색 / {guidEditorType} / 편집기를 확인 하려면 레지스트리에서 하위 키 확장 파일을 열 수 및이 수행 하는 데 가장 높은 우선 순위를 갖습니다.  
  
    2.  IDE를 호출 하는 IDE가 편집기 파일을 열 수를 확인 후 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>합니다. 편집기의이 메서드 구현은 IDE에서이 호출에 필요한 정보를 반환 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 및 새로 열린된 문서 사이트입니다.  
  
    3.  IDE와 같은 일반적인 지 속성 인터페이스를 사용 하 여 문서를 로드 하는 마지막으로, <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>합니다.  
  
    4.  IDE를 호출 하는 IDE가 이전에 계층 구조 또는 항목 계층 구조를 사용할 수 있는지 결정 했을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> 프로젝트 수준 컨텍스트를 프로젝트에서 메서드 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 에 함께 다시 전달에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 메서드를 호출 합니다.  
  
4.  반환 된 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> IDE를 호출할 때 IDE에 대 한 포인터 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> 에서 프로젝트를 프로젝트에서 편집기 get 컨텍스트를 사용 하려는 경우.  
  
     이 단계를 수행 프로젝트 제품 추가 서비스를 편집기를 수 있습니다.  
  
     호출 하 여 데이터와 함께 개체를 초기화 하는 경우 문서 뷰 또는 문서 보기 개체가 창 프레임에 배치 되어 성공적으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.LoadDocData%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트 관련 편집기 열기](../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 열려 있는 문서에 대 한 편집기 열기](../extensibility/how-to-open-editors-for-open-documents.md)   
 [파일 열기 명령을 사용하여 파일 표시](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)
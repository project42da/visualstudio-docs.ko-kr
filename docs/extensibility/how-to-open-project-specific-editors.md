---
title: "방법: 프로젝트 관련 편집기 열기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, opening a project-specific editor
- editors [Visual Studio SDK], opening project-specific editors
- projects [Visual Studio SDK], opening folders
ms.assetid: 83e56d39-c97b-4c6b-86d6-3ffbec97e8d1
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb60f482edeea1271c0f864fd5b907138e83d103
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-project-specific-editors"></a>방법: 프로젝트 관련 편집기 열기
프로젝트에서 열리는 항목 파일에는 기본적으로 해당 프로젝트에 대 한 특정 편집기에 바인딩되어 있는 경우 프로젝트 프로젝트 관련 편집기를 사용 하 여 파일을 열어야 합니다. 편집기를 선택 하기 위한에서 IDE의 메커니즘으로 파일을 위임할 수 없습니다. 예를 들어 표준 비트맵 편집기를 사용 하는 대신 프로젝트에 고유한 파일의 정보를 인식 하는 특정 비트맵 편집기를 지정 하려면이 프로젝트 관련 편집기 옵션을 사용할 수 있습니다.  
  
 IDE 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 특정 프로젝트에서 파일을 열 수를 결정할 때 메서드. 자세한 내용은 참조 [파일 열기 명령을 사용 하 여 표시 파일](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)합니다. 다음 지침을 사용 하 여 구현 하는 `OpenItem` 메서드를 사용 하려면 프로젝트 프로젝트 관련 편집기를 사용 하 여 파일을 열어야 합니다.  
  
### <a name="to-implement-the-openitem-method-with-a-project-specific-editor"></a>프로젝트 관련 편집기로 OpenItem 메서드를 구현 하려면  
  
1.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> (문서 데이터 개체로) 파일은 이미 열려 있는지 여부를 확인 하려면 메서드 (RDT_EditLock).  
  
    > [!NOTE]
    >  문서 데이터 및 문서 보기 개체에 대 한 자세한 내용은 참조 [문서 데이터와 사용자 지정 편집기에서 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)합니다.  
  
2.  파일이 이미 열려 있으면 호출 하 여 파일을 resurface는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 메서드와 IDO_ActivateIfOpen에 대 한 값을 지정 하는 `grfIDO` 매개 변수입니다.  
  
     파일이 열려 문서 호출 하는 프로젝트 이외의 다른 프로젝트에서 소유 하는 경우 열려는 편집기가 다른 프로젝트에서 사용자에 게 경고가 표시 됩니다. 다음 파일 창에 표시 됩니다.  
  
3.  텍스트 버퍼 (문서 데이터 개체)가 이미 열려 있고 다른 보기에 연결 하려는 모르는 경우 해당 보기를 후크 하는 일을 담당 합니다. 권장 되는 방법 보기 (문서 보기 개체), 프로젝트에서 인스턴스화에 다음과 같습니다.  
  
    1.  호출 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry> 에 대 한 포인터를 가져오기 위해 서비스에는 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> 인터페이스입니다.  
  
    2.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> 문서 뷰 클래스의 인스턴스를 만드는 메서드.  
  
4.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 메서드에 문서 뷰 개체를 지정 합니다.  
  
     이 메서드는 문서 창에 문서 보기 개체를 사이트입니다.  
  
5.  에 대 한 적절 한 호출을 수행는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.InitNew%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> 메서드.  
  
     이 시점에서 보기 완전히 초기화 해 서 열 수를 준비 해야 합니다.  
  
6.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 메서드를 표시 하 고 보기를 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md)   
 [방법: 열린 문서에 대한 편집기 열기](../extensibility/how-to-open-editors-for-open-documents.md)
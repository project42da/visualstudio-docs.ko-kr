---
title: "방법: 표준 편집기 열기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK], 열기"
  - "프로젝트 [Visual Studio SDK] 표준 편집기 열기"
ms.assetid: d5ce10f9-047a-4b74-aa1d-295128898b89
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 표준 편집기 열기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

표준 편집기를 열면 IDE를 파일을 프로젝트 고유 편집기를 지정 하는 대신 지정 된 파일 형식에 대 한 표준 편집기를 확인할 수 있습니다.  
  
 구현 하려면 다음 절차를 완료는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드가 있습니다.  프로젝트 파일을 표준 편집기에서 열립니다.  
  
### 표준 편집기를 사용 하는 OpenItem 메서드를 구현.  
  
1.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> \(`RDT_EditLock`\) 문서 데이터 개체 파일 이미 열려 있는지 여부를 결정 합니다.  
  
2.  파일이 이미 열려 있는 경우를 호출 하 여 파일 resurface는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 값을 지정 하는 메서드를 `IDO_ActivateIfOpen` 에 있는 `grfIDO` 매개 변수.  
  
     문서 소유 보다 호출 하는 프로젝트는 다른 프로젝트 파일이 열려 있는 경우 프로젝트를 다른 프로젝트에서 열려 있는 편집기 있는 경고를 받습니다.  파일 창 고 대 두 됩니다.  
  
3.  문서가 열려 있지 않은 경우 또는 실행 문서 테이블에서 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드 \(`OSE_ChooseBestStdEditor`\) 파일에 대 한 표준 편집기를 엽니다.  
  
     메서드를 호출 하는 경우 IDE는 다음 작업을 수행 합니다.  
  
    1.  IDE는 편집기를 검색 \/ {guidEditorType} \/ 확장 하위 키에서 레지스트리 편집기를 확인 하려면 파일을 열 수 및이 위한 가장 높은 우선 합니다.  
  
    2.  IDE는 편집기 파일을 열 수 있습니다 결정 후 IDE를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>.  이 메서드는 편집기 구현 IDE를 호출 하는 데 필요한 정보를 반환 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 와 새로 열린된 문서 사이트.  
  
    3.  마지막으로, 같은 일반적인 지 속성,이 인터페이스를 사용 하 여 문서는 IDE를 로드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>.  
  
    4.  IDE 이전 계층 또는 계층 구조 항목을 사용할 수 있는지 확인 하는 경우 IDE를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> 방법을 프로젝트 수준 컨텍스트를 가져올 수 있는 프로젝트에 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 의 전달 하는 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 메서드를 호출 합니다.  
  
4.  반환 된 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> IDE 호출 하는 경우 IDE에 대 한 포인터 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> 편집기 프로젝트에서 컨텍스트를 가져오지 수 있게 하려는 경우 프로젝트의.  
  
     이 단계를 수행 하면 편집기 추가 서비스를 제공 프로젝트 수 있습니다.  
  
     문서 보기 또는 문서 뷰 개체 창 프레임에 성공적으로 배치 된 경우 개체에 필요한 데이터를 호출 하 여 초기화 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.LoadDocData%2A>.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트에 특정 편집기 열기](../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 열린 문서에 대 한 편집기를 열어](../extensibility/how-to-open-editors-for-open-documents.md)   
 [파일 열기 명령을 사용 하 여 파일을 표시 합니다.](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)
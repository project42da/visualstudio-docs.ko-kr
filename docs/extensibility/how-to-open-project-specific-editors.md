---
title: "방법: 프로젝트에 특정 편집기 열기 | Microsoft Docs"
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
  - "프로젝트 형식에는 프로젝트에 특정 편집기 열기"
  - "편집기 [Visual Studio SDK] 프로젝트 관련 편집기 열기"
  - "프로젝트 [Visual Studio SDK] 폴더 열기"
ms.assetid: 83e56d39-c97b-4c6b-86d6-3ffbec97e8d1
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 프로젝트에 특정 편집기 열기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트에 열려 있는 항목 파일은 기본적으로 해당 프로젝트의 특정 편집기에 바인딩되어 있으면 프로젝트 프로젝트 고유 편집기를 사용 하 여 해당 파일을 열어야 합니다.  파일 편집기를 선택 하면 IDE의 메커니즘을 위임할 수 없습니다.  예를 들어, 표준 비트맵 편집기를 사용 하는 대신이 프로젝트 고유 편집기 옵션 프로젝트에 고유한 파일의 정보를 인식 하는 특정 비트맵 편집기를 지정 하려면 사용 하면 수 있습니다.  
  
 IDE 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드는 특정 프로젝트에서 파일을 열 수를 결정 하는 경우.  자세한 내용은 [파일 열기 명령을 사용 하 여 파일을 표시 합니다.](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)를 참조하십시오.  다음 지침을 사용 하 여 구현 하는 `OpenItem` 메서드를 프로젝트 파일을 프로젝트 고유 편집기를 사용 하 여 열을 사용 하려면.  
  
### 프로젝트 고유 편집기를 사용 하는 OpenItem 메서드를 구현.  
  
1.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> \(문서 데이터 개체\) 파일 이미 열려 있는지 여부를 확인 하는 메서드 \(RDT\_EditLock\).  
  
    > [!NOTE]
    >  문서 데이터 및 문서의 뷰 개체에 대 한 자세한 내용은 참조 하십시오. [문서 데이터와 사용자 지정 편집기에서 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md).  
  
2.  파일이 이미 열려 있는 경우를 호출 하 여 파일 resurface는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 메서드 및 ido\_activateifopen에 대 한 값을 지정 하는 `grfIDO` 매개 변수.  
  
     파일이 열려 있는 문서 호출 하는 프로젝트 이외의 프로젝트를 소유 하는 경우 다른 프로젝트에서 열려 있는 편집기는 사용자에 게 경고 메시지가 표시 됩니다.  파일 창 고 대 두 됩니다.  
  
3.  텍스트 버퍼 \(문서 데이터 개체\) 이미 열려 있고 다른 보기에 연결 하려는 경우 해당 보기를 연결 하기 위한 책임이 있습니다.  뷰 \(뷰 개체 문서\)에서 프로젝트를 인스턴스화할 수 있는 권장 되는 방법은 다음과 같습니다.  
  
    1.  호출 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry> 서비스에 대 한 포인터를 얻을 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> 인터페이스입니다.  
  
    2.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> 문서 뷰 클래스의 인스턴스를 만드는 방법.  
  
4.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> 문서 보기 개체를 지정 하는 메서드를.  
  
     문서 창에서 문서 보기 개체 사이트의이 메서드  
  
5.  적절 한 호출 중 하나를 수행의 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.InitNew%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> 방법.  
  
     이 시점에서 보기 완전 하 게 초기화 되어 열 수 있어야 합니다.  
  
6.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 메서드를 표시 하 고 해당 보기를 엽니다.  
  
## 참고 항목  
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md)   
 [방법: 열린 문서에 대 한 편집기를 열어](../extensibility/how-to-open-editors-for-open-documents.md)
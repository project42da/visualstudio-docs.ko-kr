---
title: "편집기 팩터리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-편집기 팩터리"
ms.assetid: cf4e8164-3546-441d-b465-e8a836ae7216
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 편집기 팩터리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기 팩터리 편집기 개체를 만들고 실제 보기 라는 창 프레임을 적용 됩니다.  문서 데이터 및 편집기와 디자이너를 만드는 데 필요한 문서의 뷰 개체를 만듭니다.  편집기 팩터리 Visual Studio 코어 편집기와 기타 표준 편집기를 작성 해야 합니다.  사용자 지정 편집기는 편집기 팩터리를 선택적으로 만들 수 있습니다.  
  
 편집기 팩터리를 구현 하 여 만들는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스입니다.  다음은 구현 하는 방법을 보여 줍니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 편집기 팩터리를 만들려면:  
  
 [!code-vb[VSSDKEditorFactories#1](../extensibility/codesnippet/VisualBasic/editor-factories_1.vb)]
 [!code-cs[VSSDKEditorFactories#1](../extensibility/codesnippet/CSharp/editor-factories_1.cs)]  
  
 편집기 처음 처리 해당 편집기에서 파일 형식을 열 때 로드 됩니다.  특정 편집기 또는 기본 편집기를 열 수 있습니다.  기본 편집기를 선택 하면 통합된 개발 환경 \(IDE\) 올바른 열 편집기를 결정 하 고 엽니다.  자세한 내용은 [프로젝트의 파일 편집기 열리는 결정합니다.](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)를 참조하십시오.  
  
## 편집기 팩터리를 등록합니다.  
 생성 한 편집기를 사용 하기 전에 먼저 처리할 수 있는 파일 확장명을 포함 하 여,에 대 한 정보를 등록 해야 합니다.  
  
 Vspackage를 관리 되는 코드로 작성 된 경우 패키지 관리 프레임 워크 \(MPF\) 메서드를 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> 하면 VSPackage 로드 된 후 편집기 팩터리를 등록 합니다.  Vspackage를 관리 되지 않는 코드를 작성 하 고 사용자 편집기 팩터리를 사용 하 여 등록 해야 합니다 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors> 서비스 합니다.  
  
### 관리 코드를 사용 하 여 편집기 팩터리 등록  
 사용자 편집기 팩터리를 Vspackage에 등록 해야는 `Initialize` 방법입니다.  먼저 호출 `base.Initialize`, 다음 호출 <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> 의 각 편집기 팩터리  
  
 관리 되는 코드에 없는 편집기 팩터리를 등록 하지 않아도 Vspackage는이 처리 합니다 때문 에입니다.  또한 편집기 팩터리를 구현 하는 경우 <xref:System.IDisposable>에 등록 된 경우 자동으로 삭제 됩니다.  
  
### 관리 되지 않는 코드를 사용 하 여 편집기 팩터리 등록  
 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 구현을 사용 편집기 패키지에 `QueryService` 메서드를 호출 하 `SVsRegisterEditors`.  이 작업에 대 한 포인터를 반환 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> 메서드 구현을 전달의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 인터페이스.  Mplement 해야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> 는 별도 클래스에 있습니다.  
  
## 편집기 팩터리 등록  
 Visual Studio 편집기 팩터리를 사용 하 여 편집기를 로드 하는 경우 다음과 같은 프로세스가 발생 합니다.  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 시스템 호출 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
2.  이 메서드는 편집기 팩터리를 반환합니다.  그러나 편집기의 패키지 프로젝트 시스템 편집기를 실제로 필요할 때까지 로드 Visual Studio 연기 합니다.  
  
3.  편집기 프로젝트 시스템에 필요한 경우 Visual Studio 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>, 문서와 문서 보기에 데이터 개체를 반환 하는 특수화 된 메서드.  
  
4.  경우 Visual Studio 편집기 팩터리 사용 하 여 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 문서 데이터 객체와 문서 뷰 개체를 반환 하 고 Visual Studio 다음 문서 창을 만들고 문서 보기 개체를 배치한 후에 실행 중인 문서 \(RDT\) 문서 데이터 개체에 대 한 항목이 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>   
 [실행 중인 Document 테이블](../extensibility/internals/running-document-table.md)
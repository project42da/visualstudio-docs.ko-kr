---
title: "프로젝트의 파일 편집기 열리는 결정합니다. | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK], 파일을 엽니다 편집기를 결정 합니다."
  - "프로젝트 [Visual Studio SDK] 파일을 엽니다 편집기를 결정 합니다."
  - "프로젝트 형식 편집기를 결정 하는 파일을 열"
  - "지 속성 파일을 엽니다 편집기를 결정 합니다."
ms.assetid: acbcf4d8-a53a-4727-9043-696a47369479
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트의 파일 편집기 열리는 결정합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자가 프로젝트를 열 때 환경 결국 적절 한 편집기 또는 디자이너는 파일을 여는 폴링 프로세스를 통해 이동 합니다.  초기 절차는 환경에 의해 사용 되는 표준 및 사용자 지정 편집기에 대 한 동일 합니다.  환경 파일을 열 때 사용할 편집기를 폴링할 때는 다양 한 조건 사용 하 고 있는 VSPackage 환경으로이 과정에서 조정 해야 합니다.  
  
 예를 들어, 사용자가 선택할 때는  **열기** 명령을  **파일** 메뉴에서 다음을 선택 하 고 `filename`.rtf \(또는 다른 파일 확장명이.rtf\) 환경 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 결국 솔루션에서 모든 프로젝트 인스턴스를 순환 하는 각 프로젝트에 대 한 구현을.  프로젝트 우선 순위에 따라 청구 된 문서를 식별 하는 플래그 집합을 반환 합니다.  가장 높은 우선 순위를 사용 하 여 환경에 적합 한 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드가 있습니다.  자세한 내용은 폴링 프로세스에 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
 기타 파일 프로젝트는 다른 프로젝트에서 주장 하 고 없는 모든 파일을 주장 합니다.  이 방법은 표준 편집기 열기 전에 사용자 지정 편집기 문서를 열 수 있습니다.  환경 기타 파일 프로젝트 파일을 주장 하는 경우 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드는 표준 편집기로 파일을 엽니다.  환경.rtf 파일을 처리 하는 내부 목록 중 하나에 대해 등록 된 편집기를 확인 합니다.  이 목록은 레지스트리의 다음 키에 있습니다.  
  
 HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\ \<`버전`\> \\Editors\\ {\<`편집기 팩터리 guid`\>} \\Extensions\]  
  
 또한 환경 HKEY\_CLASSES\_ROOT\\CLSID 키에 하위 키 DocObject 개체의 클래스 식별자를 검사 합니다.  파일 확장명이 있을 경우에 포함 된 버전의 Microsoft Word와 같은 응용 프로그램을 내부 Visual Studio 만들어집니다.  이러한 문서 개체를 구현 하는 복합 파일 이어야 합니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage> 해야 인터페이스 또는 개체를 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 인터페이스입니다.  
  
 .Rtf 파일의 레지스트리 편집기 팩토리 없음 경우 환경 HKEY\_CLASSES\_ROOT \\.rtf 키에 찾고 지정 된 편집기가 열립니다.  파일 확장명을 HKEY\_CLASSES\_ROOT 없으면 환경 Visual Studio 코어 텍스트 편집기를 사용 하 여 텍스트 파일인 경우 파일을 엽니다.  
  
 코어 텍스트 편집기에 오류가 발생 하는 경우 파일은 텍스트 파일이 아닙니다 경우 환경에 바이너리 편집기에 대 한 파일 사용 발생 합니다.  
  
 환경 편집기.rtf 확장명에 대 한 레지스트리를 찾는 경우이 편집기 팩터리 구현 VSPackage 로드 합니다.  환경 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드는 새 VSPackage.  VSPackage 호출 `QueryService` 에 대 한 `SID_SVsRegistorEditor`사용 하 여 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> 메서드를 사용 하 여 환경 편집기 팩터리를 등록 하려면.  
  
 환경 지금 내부 목록 새로 등록 된 편집기 팩터리.rtf 파일을 찾으려면 등록 된 편집자의 단계.  환경 구현을 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 만들려면 파일 이름 및 뷰 형식에 전달 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>   
 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>
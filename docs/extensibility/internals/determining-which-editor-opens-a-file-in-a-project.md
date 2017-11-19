---
title: "편집기는 프로젝트의 파일을 열 결정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], determining which editor opens a file
- projects [Visual Studio SDK], determining which editor opens file
- project types, determining which editor opens a file
- persistence, determining which editor opens a file
ms.assetid: acbcf4d8-a53a-4727-9043-696a47369479
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc0105b56f0a33a86953c95e3d36f5d7f00bcd37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="determining-which-editor-opens-a-file-in-a-project"></a>편집기 열리는 프로젝트의 파일 확인
사용자는 프로젝트에서 파일을 열면 환경을 결국 해당 편집기 또는 해당 파일에 대 한 디자이너를 열어 폴링 프로세스를 통해 이동 합니다. 환경에서 사용 하는 초기 프로시저 표준 및 사용자 지정 편집기에 대해 같습니다. 환경 파일을 사용할 편집기를 폴링할 때 다양 한 기준 사용 하 여 및이 프로세스 동안 환경과 VSPackage 조정 해야 합니다.  
  
 사용자가 선택할 때을 예를 들어는 **열려** 명령을 **파일** 메뉴 한 다음 선택 `filename`.rtf (또는 다른 파일 확장명이.rtf) 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 솔루션의 모든 프로젝트 인스턴스를 결국 순환 각 프로젝트에 대 한 구현입니다. 프로젝트의 우선 순위에 따라 문서에 대 한 클레임을 식별 하는 플래그 집합을 반환 합니다. 가장 높은 우선 순위를 사용 하 여 환경에서 적절 한 호출. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드. 폴링 프로세스에 대 한 자세한 내용은 [추가 프로젝트 및 프로젝트 항목 템플릿](../../extensibility/internals/adding-project-and-project-item-templates.md)합니다.  
  
 기타 파일 프로젝트는 다른 프로젝트에서 요구 하지 않은 모든 파일을 요구 합니다. 이러한 방식으로 사용자 지정 편집기 전에 열고 문서 표준 편집기를 찾아서 열입니다. 환경을 호출 하는 기타 파일 프로젝트 파일을 클레임를 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드를 표준 편집기로 파일을 엽니다. .Rtf 파일을 처리 하는 하나에 대해 등록 된 편집기의 내부 목록을 검사 하는 환경입니다. 이 목록은의 레지스트리에 다음 키에 있습니다.  
  
 [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<`version`> \Editors\\{<`editor factory guid`>} \Extensions]  
  
 또한 환경 하위 키 DocObject이 있는 모든 개체에 대 한 HKEY_CLASSES_ROOT\CLSID 키의 클래스 식별자를 확인 합니다. 파일 확장명 전역 어셈블리 캐시는 Microsoft Word, 응용 프로그램의 포함된 된 Visual Studio 내부 만들어집니다. 이러한 문서 개체를 구현 하는 복합 파일 이어야 합니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage> 개체나 인터페이스를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 인터페이스입니다.  
  
 레지스트리에서.rtf 파일에 대 한 편집기 팩터리가 없는 경우는 HKEY_CLASSES_ROOT에서 환경을 찾습니다 \\.rtf 키와 여기에 지정 된 편집기가 열립니다. HKEY_CLASSES_ROOT에 파일 확장명이 없는, 환경 파일을 열려면 텍스트 파일인 경우 Visual Studio 핵심 텍스트 편집기를 사용 합니다.  
  
 핵심 텍스트 편집기에 실패 하면 파일이 텍스트 파일을 다음 환경을 사용 하 여 해당 바이너리 편집기 파일에 대 한 발생 하 합니다.  
  
 환경이 레지스트리에서 해당.rtf 확장에 대 한 편집기를 찾지를 경우이 편집기 팩터리를 구현 하는 VSPackage를 로드 합니다. 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드 새 VSPackage 합니다. VSPackage 호출 하 여 `QueryService` 에 대 한 `SID_SVsRegistorEditor`를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> 환경과 편집기 팩터리를 등록 합니다.  
  
 환경 이제 다시 내부 목록을 검사의 등록 된 편집기.rtf 파일에 대 한 새로 등록 된 편집기 팩터리를 찾을 수 있습니다. 환경의 구현이 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 만들려는 파일 이름 및 뷰 형식에 전달 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>   
 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>
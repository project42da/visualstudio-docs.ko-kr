---
title: "언어 서비스 및 핵심 편집기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - language services
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1528bc685577082df997535a680c372620821de0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="language-services-and-the-core-editor"></a>언어 서비스 및 핵심 편집기
Visual Studio의 편집기는 언어 서비스에 자주 연결 됩니다. 특히, 구문 색 지정, 문 완성, IntelliSense 및 텍스트 서식 지정 언어 서비스를 제공합니다.  
  
## <a name="core-editors-and-document-data-objects"></a>코어 편집기와 문서 데이터 개체  
 코어 편집기에 액세스 하면 문서 데이터 및 문서 보기 개체 만들지 않으면 합니다. IDE를 만들고이 두 개체를 제어 하 고 팩터리 구현 하면 편집기의 적절 한 호출을 수행 하 여 해당에 대 한 핸들을 가져와야 합니다.  
  
 자세한 내용은 참조 [프로젝트의 파일을 열 편집기 결정](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)합니다.  
  
## <a name="language-services-and-the-core-editor"></a>언어 서비스 및 핵심 편집기  
 언어 서비스를 구현 하 여 문서 보기에 데이터가 표시 되는 방식을 제어할 수 있습니다. 언어 서비스 정보 및 Visual c + +와 같은 지정된 된 언어에 관련 된 동작을 제공 합니다. 텍스트 버퍼를 만들고 여는 문서에 대 한 파일 이름 확장명을 결정 하는 경우 텍스트 버퍼에 의해이 파일 이름 확장명이 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Editors 레지스트리 키에서와 연결 된 언어 서비스가 결정 \\{YourLanguageService GUID} \Extensions 합니다. 다음 절차를 로드 하는 표준 VSPackage VSPackage를 로드 하 고 언어 서비스의 인스턴스가 만들어집니다.  
  
 기본 언어 서비스는 다음 그림에 표시 됩니다.  
  
 ![언어 서비스 모델 그래픽](../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
핵심 편집기와 언어 서비스 개체  
  
 문서 데이터 개체로 코어 편집기에 대 한 텍스트 버퍼 라고 하며으로 표시 됩니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체입니다. 문서 뷰 개체를 텍스트 뷰라고 하며으로 표시 됩니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> 개체입니다. 이 두 개체 코어 편집기의 통합된 뷰를 제공 하는 언어 서비스를 통해 협력 합니다. 텍스트 버퍼 및 문서 창에 텍스트 보기 표시의 정보는 코드 창을 호출 됩니다. 코드 창 문서 코드 창 관리자에서 관리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다.](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [IntelliSense 호스팅](../extensibility/intellisense-hosting.md)   
 [포함 된 언어](../extensibility/contained-languages.md)   
 [레거시 언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)
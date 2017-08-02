---
title: "언어 서비스 및 코어 편집기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-언어 서비스"
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 언어 서비스 및 코어 편집기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기에서 Visual Studio 언어 서비스와 자주 연관 됩니다.  특히 구문 색상 표시, 문 완성, IntelliSense, 및 텍스트 서식을 언어 서비스를 제공합니다.  
  
## 코어 편집기와 문서 데이터 개체  
 문서 데이터 및 문서의 뷰 개체의 핵심 편집기에 액세스할 때 만들지 마십시오.  IDE를 만들고이 두 개체를 제어 하 고 적절 한 통화를 편집기 팩터리 구현 하 여 핸들을 가져옵니다.  
  
 자세한 내용은 [프로젝트의 파일 편집기 열리는 결정합니다.](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)를 참조하십시오.  
  
## 코어 편집기와 언어 서비스  
 언어 서비스를 구현 하 여 문서 보기에서 데이터가 표시 되는 방법을 제어할 수 있습니다.  언어 서비스 정보 및 Visual c \+ \+와 같은 지정 된 언어와 관련 된 동작을 제공 합니다.  열고 있는 문서에 대 한 파일 이름 확장명을 확인 하 고 텍스트 버퍼를 만들 때 텍스트 버퍼에서 {YourLanguageService GUID} HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Editors\\ \\Extensions 레지스트리 키에이 파일 이름 확장명이 연결 된 언어 서비스를 결정 합니다.  하면 VSPackage 로드 하 고 절차는 표준 VSPackage 로드 및 언어 서비스의 인스턴스가 만들어집니다.  
  
 기본 언어 서비스는 다음 그림에 나와 있습니다.  
  
 ![언어 서비스 모델 그래픽](~/extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
코어 편집기와 언어 서비스 개체  
  
 코어 편집기 문서의 데이터 개체에서 텍스트 버퍼 라고 하며 표시 됩니다 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체입니다.  문서 보기 개체 텍스트 뷰에서 호출 되 고 표시 됩니다 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> 개체입니다.  이러한 두 개체는 서로 코어 편집기의 통합 된 보기를 제공 하는 언어 서비스를 통해 작동 합니다.  텍스트 버퍼 및 텍스트 보기 표시 합니다 문서 창에서 코드 창이 호출 됩니다.  코드 창의 문서 코드 창 관리자가 관리 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다.](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [IntelliSense 호스팅](../extensibility/intellisense-hosting.md)   
 [포함 된 언어](../extensibility/contained-languages.md)   
 [언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)
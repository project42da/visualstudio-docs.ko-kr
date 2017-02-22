---
title: "사용자 지정 도구 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage를 사용자 지정 도구"
  - "도구 [Visual Studio] 사용자 지정"
  - "사용자 지정 도구"
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# 사용자 지정 도구
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

*사용자 지정 도구* 도구는 프로젝트에서 항목을 연결 하 고 파일을 저장할 때마다 해당 도구를 실행할 수 있습니다.  특정 사용자 지정 도구 라고도 하는  *단일 파일 생성기가*, 자주 코드, 또는 그 반대로 데이터를 생성 하는 번역 작업을 구현 하는 데 사용 됩니다.  예를 들어, 단일 파일 생성기가 만든 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 소스.settings 및.resx 파일의 코드입니다.  생성 된 소스 코드 강력한.settings 및.resx 파일의 데이터에에서 액세스합니다.  [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 형식을 지 원하는 사용자 지정 도구입니다.  [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)]프로젝트 형식에서는 그렇지 않습니다.  또한 프로젝트 형식을 직접 사용자 지정 도구를 지원할 수 있습니다.  
  
 사용자 지정 도구는 구현 하는 등록 된 구성 요소는 `IVsSingleFileGenerator` 인터페이스입니다.  
  
 사용자 지정 도구와 연결 된는 `ProjectItem` 개체, 인터페이스 및 디자이너 및 편집기와 같은 됩니다.  표시 되는 파일은 사용자 지정 도구는는 `ProjectItem` 로 입력 하 고 파일 이름을 제공 하는 것은 새 파일을 작성에 `DefaultExtension` 메서드.  
  
## 단원 내용  
 [단일 파일 생성기를 구현합니다.](../../extensibility/internals/implementing-single-file-generators.md)  
 사용 하는 방법에 설명의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 인터페이스는 사용자 지정 도구를 구현할 수 있습니다.  
  
 [프로젝트의 기본 네임스페이스 확인](../../misc/determining-the-default-namespace-of-a-project.md)  
 사용 중인 언어에 따라 올바른 네임 스페이스를 확인 하는 방법에 설명 합니다.  
  
 [단일 파일 생성기를 등록 하는 중](../../extensibility/internals/registering-single-file-generators.md)  
 모든 레지스트리 항목에 대 한 사용자 지정 도구에 대해 설명합니다.  
  
 [비주얼 디자이너에 형식을 노출합니다.](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 프로젝트 시스템 지원을 비주얼 디자이너 액세스 생성 클래스 및 형식에 대 한 임시 이식 가능한 실행 파일 \(PE\) 파일을 통해 제공 하는 방법을 설명 합니다.  
  
 [프로젝트 항목의 속성을 유지](../../extensibility/persisting-the-property-of-a-project-item.md)  
 프로젝트 파일에 소스 파일의 작성자와 같은 프로젝트 항목 속성을 저장 하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 에 대 한 자세한 정보를 제공의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, 어떤 변환 단일 입력된 파일 컴파일 또는 프로젝트에 추가 하는 단일 출력 파일에 있습니다.  
  
 <xref:EnvDTE.ProjectItem>  
 설명에 `ProjectItem` 인터페이스는 프로젝트에 있는 항목을 나타냅니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 에 대 한 자세한 정보를 제공의 `DefaultExtension` 출력 파일 이름으로 지정 된 파일 이름 확장명을 검색 하는 방법입니다.  
  
## 관련 단원  
 [프로젝트 확장](../../extensibility/extending-projects.md)  
 사용 하는 방법에 설명 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 및 소스 제어를 구현 하는 코드 파일 및 리소스 파일을 구성 하는 솔루션입니다.
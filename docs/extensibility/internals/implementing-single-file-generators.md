---
title: "단일 파일 생성기를 구현합니다. | Microsoft Docs"
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
  - "구현 하는 사용자 지정 도구"
  - "확장성 프로젝트 [Visual Studio SDK]"
  - "프로젝트 [Visual Studio SDK] 사용자 지정 도구를 관리 합니다."
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 단일 파일 생성기를 구현합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 지정 도구\-단일 파일 생성기와 라고도 합니다\-확장 하는 데 사용할 수 있습니다의 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 시스템에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  구현 하는 COM 구성 요소는 사용자 지정 도구가 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 인터페이스입니다.  이 인터페이스를 사용 하 여 사용자 지정 도구를 하나의 출력 파일로 단일 입력된 파일으로 변환 합니다.  소스 코드 변환의 결과가 될 수 있습니다 또는 기타 출력에 유용 합니다.  사용자 지정 도구에서 생성 한 코드 파일의 두 가지 예는 비주얼 디자이너 및 WSDL \(웹 서비스 설명 언어\)을 사용 하 여 생성 한 파일의 변경 내용에는 생성 된 코드입니다.  
  
 로드 된 사용자 지정 도구 또는 입력된 파일을 저장 하는 경우 프로젝트 시스템에서 걸의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 메서드를 참조를 전달 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> 는 도구 수 있습니다 보고 진행 상황 사용자에 게 콜백 인터페이스를.  
  
 사용자 지정 도구에서 생성 하는 출력 파일은 입력된 파일에 종속 된 프로젝트에 추가 됩니다.  사용자 지정 도구 구현에서 반환 되는 문자열을 기반으로 하는 출력 파일의 이름을 자동으로 프로젝트 시스템을 결정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 구현 해야 하는 사용자 지정 도구는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 인터페이스입니다.  필요에 따라 지원 되는 사용자 지정 도구는 <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> 입력된 파일 이외의 소스에서 정보를 검색할 수 있는 인터페이스입니다.  사용자 지정 도구를 사용 하기 전에 어떤 경우에 시스템 또는 등록 해야는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로컬 레지스트리.  사용자 지정 도구를 등록에 대 한 자세한 내용은 [단일 파일 생성기를 등록 하는 중](../../extensibility/internals/registering-single-file-generators.md).  
  
## 참고 항목  
 [프로젝트의 기본 네임스페이스 확인](../../misc/determining-the-default-namespace-of-a-project.md)   
 [비주얼 디자이너에 형식을 노출합니다.](../../extensibility/internals/exposing-types-to-visual-designers.md)
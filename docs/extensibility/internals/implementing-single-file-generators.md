---
title: 단일 파일 생성기 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71db8036634cfc266db3c585c48317262f48b367
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-single-file-generators"></a>단일 파일 생성기를 구현합니다.
사용자 지정 도구-단일 파일 생성기 라고도-사용을 확장할 수 있습니다는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 시스템에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 사용자 지정 도구는를 구현 하는 COM 구성 요소는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 인터페이스입니다. 이 인터페이스를 사용 하는 사용자 지정 도구를 단일 출력 파일에 단일 입력된 파일이 변형 합니다. 소스 코드에는 변환의 결과가 수 있습니다 또는 다른 출력 유용 합니다. 사용자 지정 도구에서 생성 된 코드 파일의 두 가지 예는 비주얼 디자이너 겸 WSDL 웹 서비스 설명 언어 ()를 사용 하 여 생성 된 파일의 변경 내용에 대 한 응답으로 생성 된 코드입니다.  
  
 를 사용자 지정 도구를 로드 하거나 입력된 파일을 저장할 때 프로젝트 시스템에서는 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 메서드를 전달에 대 한 참조는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> 콜백 인터페이스를 그에 따라 도구 진행 상태는 사용자에 보고할 수 있습니다.  
  
 사용자 지정 도구가 생성 하는 출력 파일은 입력된 파일에 대 한 종속성을 사용 하 여 프로젝트에 추가 됩니다. 프로젝트 시스템은 자동으로 사용자 지정 도구 구현에 의해 반환 되는 문자열에 따라 출력 파일의 이름을 결정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>합니다.  
  
 사용자 지정 도구를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 인터페이스입니다. 필요에 따라 사용자 지정 도구 지원는 <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> 입력된 파일 이외의 원본에서 정보를 검색 하는 인터페이스입니다. 어떤 경우 든, 사용자 지정 도구를 사용 하려면 먼저 등록 해야 시스템과 또는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로컬 레지스트리 합니다. 사용자 지정 도구를 등록 하는 방법에 대 한 자세한 내용은 참조 하십시오. [단일 파일 생성기 등록](../../extensibility/internals/registering-single-file-generators.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비주얼 디자이너에 형식 노출](../../extensibility/internals/exposing-types-to-visual-designers.md)
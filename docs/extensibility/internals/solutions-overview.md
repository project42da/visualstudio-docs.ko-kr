---
title: "솔루션 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "솔루션에 대 한 솔루션"
ms.assetid: 3b21e3a1-170a-4485-941e-6b04b7b27886
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 솔루션 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션은 응용 프로그램을 만드는 함께 작동 하는 하나 이상의 프로젝트의 그룹입니다. 솔루션에 대 한 프로젝트 및 상태 정보는 두 개의 서로 다른 솔루션 파일에 저장 됩니다. 솔루션 \(.sln\) 파일은 텍스트 기반 소스 코드 제어에서 및 사용자 간에 공유 될 수 있습니다. 솔루션 사용자 옵션 \(.suo\) 파일을 이진입니다. 결과적으로,.suo 파일에 소스 코드 제어를 배치할 수 및 사용자 관련 정보를 포함 합니다.  
  
 모든 VSPackage 어떤 유형의 솔루션 파일에 쓸 수 있습니다. 파일 특성으로 인해 두 가지 다른 인터페이스 구현에 쓸 수 있습니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> 인터페이스.sln 파일을 텍스트 정보를 기록 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> 인터페이스 이진 스트림을.suo 파일에 씁니다.  
  
> [!NOTE]
>  프로젝트는 솔루션 파일로 자체에 대 한 항목을 명시적으로 작성 하지 않아도 환경 프로젝트를 처리합니다. 따라서 솔루션 파일에만 추가 콘텐츠를 추가 하려는 경우가 아니면 필요가 없습니다를 이러한 방식으로 VSPackage를 등록 합니다.  
  
 솔루션 지 속성을 지 원하는 각 VSPackage 세 개의 인터페이스를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> 인터페이스에는 환경에 의해 구현 되 고 VSPackage에서 호출 되 면 및 `IVsPersistSolutionProps` 및 `IVsPersistSolutionOpts`, VSPackage에서 모두 구현 하는 됩니다.`IVsPersistSolutionOpts` 인터페이스만 개인 정보를 VSPackage.suo 파일에 쓰여지도록 하는 경우에 구현 해야 합니다.  
  
 솔루션을 열 때 다음 프로세스가 수행이 됩니다.  
  
1.  환경 솔루션을 읽습니다.  
  
2.  환경에서 발견 한 경우는 `CLSID`, 해당 VSPackage를 로드 합니다.  
  
3.  경우 VSPackage 로드 되는 환경 호출 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> VSPackage 필요로 하는 인터페이스에 대 한 인터페이스입니다.  
  
    1.  .Sln 파일을 읽을 때 환경 호출 `QueryInterface` 에 대 한 `IVsPersistSolutionProps`합니다.  
  
    2.  .Suo 파일을 읽을 때 환경 호출 `QueryInterface` 에 대 한 `IVsPersistSolutionOpts`합니다.  
  
 이러한 파일의 사용에 관련 된 특정 정보를 찾을 수 있습니다 [솔루션 \(합니다. Sln\) 파일](../../extensibility/internals/solution-dot-sln-file.md) 및 [솔루션 사용자 옵션 \(합니다. Suo\) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)합니다.  
  
> [!NOTE]
>  세 번째 빌드에서 제외 하 고 두 개의 프로젝트로 구성 중 구성 된 새 솔루션 구성을 만들려는 경우 속성 페이지 UI 또는 자동화를 사용 해야 합니다. 솔루션 빌드 관리자 구성 및 해당 속성은를 직접 변경할 수 없지만 사용 하 여 솔루션 빌드 관리자를 조작할 수는 `SolutionBuild` DTE 자동화 모델의 클래스입니다. 솔루션을 구성 하는 방법에 대 한 자세한 내용은 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>
---
title: "사용자 지정 도구 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7589c9a2aedf987af79689e8babccb554fbb4ccc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-tools"></a>사용자 지정 도구
*사용자 지정 도구* 도구 항목을 프로젝트에 연결 하 고 해당 도구를 실행 하 여 파일을 저장할 때마다 수 있도록 합니다. 특정 사용자 지정 도구 라고도 *단일 파일 생성기*, 자주 그 반대의 데이터에서 코드를 생성 하는 변환기를 구현 하는 데 사용 됩니다. 예를 들어, 단일 파일 생성기 만들 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 소스.settings 및.resx 파일에서 코드입니다. 생성 된 소스 코드.settings 및.resx 파일의 데이터에 대 한 강력한 형식의 액세스를 제공합니다. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 형식; 사용자 지정 도구를 지원 합니다. [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트 형식은 그렇지 않습니다. 사용자 고유의 프로젝트 형식을 사용자 지정 도구도 지원할 수 있습니다.  
  
 사용자 지정 도구는를 구현 하는 등록 된 구성 요소는 `IVsSingleFileGenerator` 인터페이스입니다.  
  
 와 연결 된 사용자 지정 도구는 `ProjectItem` 개체 인터페이스를 디자이너와 편집기와 같습니다. 사용자 지정 도구 사용 나타내는 파일은 `ProjectItem` 입력로의 이름은에서 제공 되는 새 파일을 쓰는 `DefaultExtension` 메서드.  
  
## <a name="in-this-section"></a>섹션 내용  
 [단일 파일 생성기 구현](../../extensibility/internals/implementing-single-file-generators.md)  
 사용 하는 방법에 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> 사용자 지정 도구를 구현 하는 인터페이스입니다.  
  
 [단일 파일 생성기 등록](../../extensibility/internals/registering-single-file-generators.md)  
 사용자 지정 도구에 대 한 모든 레지스트리 항목에 대 한 설명을 제공합니다.  
  
 [비주얼 디자이너에 형식 노출](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 어떻게 프로젝트 시스템 지원을 제공 액세스 생성 클래스 및 형식에 대 한 비주얼 디자이너에 대 한 임시 pe (이식 가능) 파일을 통해 설명 합니다.  
  
 [프로젝트 항목의 속성 유지](../../extensibility/persisting-the-property-of-a-project-item.md)  
 프로젝트 파일에서 소스 파일의 작성자와 같은 프로젝트 항목 속성을 유지 하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 에 대 한 세부 정보를 제공는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, 컴파일된 하거나 프로젝트에 추가할 수 있는 단일 출력 파일에 대 한 단일 입력된 파일을 변환 하는 합니다.  
  
 <xref:EnvDTE.ProjectItem>  
 설명의 `ProjectItem` 프로젝트에서 항목을 나타내는 인터페이스입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 에 대 한 세부 정보를 제공는 `DefaultExtension` 메서드 출력 파일 이름으로 지정 된 파일 이름 확장명을 검색 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 확장](../../extensibility/extending-projects.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 및 솔루션 코드 파일 및 리소스 파일 및 소스 제어를 구현 하는 방법을 구성할 수 있습니다.
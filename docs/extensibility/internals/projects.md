---
title: "프로젝트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "솔루션[Visual Studio]"
  - "사용자 지정 도구 [Visual Studio SDK]"
  - "프로젝트 하위 형식 [Visual Studio SDK]"
  - "프로젝트 [Visual Studio SDK]"
  - "프로젝트 형식 [Visual Studio SDK]"
ms.assetid: 237742e4-a638-4d5b-a9b3-6a69d627763c
caps.latest.revision: 43
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 43
---
# 프로젝트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 프로젝트는 개발자가 소스 코드 파일 및 기타 리소스에 표시를 구성 하는 데 사용할 컨테이너 **솔루션 탐색기**합니다. 일반적으로 프로젝트는 파일에 대 한 예를 들어.csproj 파일을 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 소스 코드 파일 및 비트맵 파일 같은 리소스에 대 한 참조를 저장 하는 프로젝트입니다. 구성, 빌드, 디버그 및 소스 코드를 배포할 수 있도록 프로젝트, 웹 서비스 및 데이터베이스 및 기타 리소스에 대 한 참조입니다. Vspackage를 확장할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 세 가지 주요 방법으로 프로젝트 시스템: *프로젝트 형식*, *하위 프로젝트*, 및 *사용자 지정 도구*합니다.  
  
 언어 프로젝트 시스템의 종단 간 샘플을 참조는 Visual Studio IronPython 샘플 심층 분석에는 [VSSDK 샘플](../../misc/vssdk-samples.md)합니다.  
  
## 단원 내용  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 *프로젝트 형식* 새로운 종류의 프로그래밍 언어 등의 프로젝트에 대 한 지원을 추가 합니다. 예를 들어, 각 언어는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 지원에는 고유한 프로젝트 형식이 고 IronPython 통합 샘플 IronPython 언어에 대 한 프로젝트 형식에 포함 되어 있습니다. 만들어야 언어에 대 한 프로젝트 형식이 아닌 다른 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], 항목은 작성, 디버깅, 배포 및 표시 방법을에 맞게 **솔루션 탐색기**합니다. 자세한 내용은 [프로젝트 형식](../../extensibility/internals/project-types.md) 및 [VSSDK 샘플](../../misc/vssdk-samples.md)를 참조하세요.  
  
 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)  
 *하위 프로젝트* 프로젝트 형식에 기반 하 고 프로젝트 빌드, 디버깅 및 배포 하는 방법을 사용자 지정할 데 사용할 수 있습니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 스마트 장치 프로젝트, 프로젝트 하위 형식 사용 개발 컴퓨터에서 대상 장치에는 새로 작성 하는 프로그램을 복사 하 여 배포를 사용자 지정 합니다.[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 하위 형식;에 대 한 기준으로 사용할 수 프로젝트 형식 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트 형식 수 없습니다. 사용자 고유의 프로젝트 형식은 데도 사용할 수 있습니다 기준으로 프로젝트 하위 유형입니다. 자세한 내용은 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)을 참조하세요.  
  
 [웹 프로젝트](../../extensibility/internals/web-projects.md)  
 웹 응용 프로그램을 다시 만들 수 있는 웹 프로젝트에 설명 합니다.  
  
 [새 프로젝트 생성: 내부적으로 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) 및 [새 프로젝트 생성: 내부적으로 2 부](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)  
 새 프로젝트를 만들 때 실제로 수행에 대해 설명 합니다.  
  
 [VSSDK 샘플](../../misc/vssdk-samples.md)  
 샘플에서는 설명의 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 을 처리 하는 프로젝트 및 솔루션.  
  
## 관련 단원  
 [NIB: 컨테이너로 서의 프로젝트](http://msdn.microsoft.com/ko-kr/87d40f63-f487-4767-8963-64beec27ba1b)  
 프로젝트 및 프로젝트 항목 간의 관계를 설명 합니다.
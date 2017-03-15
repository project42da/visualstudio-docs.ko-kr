---
title: "프로젝트 하위 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "하위 프로젝트 [Visual Studio SDK]"
  - "프로젝트 하위 형식 [Visual Studio SDK]"
ms.assetid: d235b47b-cf11-4d47-a63f-e33d9d16105d
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 프로젝트 하위 형식
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

하위 프로젝트를 사용 하면 사용자 지정 하거나 flavor의 프로젝트 시스템의 동작 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 사용자를 추가 하거나 항목을 필터링 프로젝트 파일에서 추가 데이터를 저장 포함는 **새 항목 추가** 어셈블리는 디버깅 및 배포 하는 방법을 제어 하는 대화 상자에서 프로젝트를 확장 하 고 **속성 페이지** 대화 상자입니다. Vspackage는 프로젝트 하위 형식 COM 집계를 사용 하 여 구현 합니다.  
  
> [!NOTE]
>  Visual c \+ \+ 프로젝트 시스템에서 하위 프로젝트를 지원 하지 않습니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 자체 프로젝트 하위 형식을 사용 하 여 SQL Server 및 스마트 장치 프로젝트를 구현 합니다.  
  
## 단원 내용  
 [프로젝트 하위 형식 디자인](../../extensibility/internals/project-subtypes-design.md)  
 하위 프로젝트의 개념을 설명 합니다.  
  
 [프로젝트 하위 초기화 시퀀스](../../extensibility/internals/initialization-sequence-of-project-subtypes.md)  
 설명 하 여 프로그래밍 방식으로 프로젝트 하위 형식 초기화 시퀀스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경입니다.  
  
 [속성 및 프로젝트 하위 형식에 의해 확장 메서드](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)  
 기능 및 하위 프로젝트를 사용 하 여 가장 자주 확장 하는 방법에 대 한 자세한 설명을 제공 합니다.  
  
 [MSBuild 프로젝트 파일에 데이터를 유지](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)  
 프로젝트 파일에 데이터를 유지 하는 방법 및 사용 하는 방법에 설명 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> 프로젝트 하위 집계 수준에서 프로젝트 파일에서 데이터를 유지 관리할 수 있습니다.  
  
 [프로젝트 속성 사용자 인터페이스](../../extensibility/internals/project-property-user-interface.md)  
 프로젝트 하위 형식에서 프로젝트를 수정할 수는 방법에 대해 설명 **속성 페이지** 대화 상자입니다.  
  
 [기본 프로젝트의 개체 모델 확장](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)  
 프로젝트 하위 형식 Automation Extender을 사용 하 여 자동화 개체 모델을 확장 하는 방법에 대 한 정보를 제공 합니다.  
  
 [기여 하는 새 항목 추가 대화 상자](../../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)  
 항목을 추가 하는 방법에 설명 된 **새 항목 추가** 대화 상자입니다.  
  
 [프로젝트 파일에서 데이터를 저장합니다.](../../extensibility/saving-data-in-project-files.md)  
 프로젝트 하위 저장 하 고 관리 하는 패키지 프레임 워크 \(MPF\)를 사용 하 여 프로젝트 파일에서 하위 형식의 특정 데이터를 검색할 수 방법에 대해 설명 합니다.  
  
 [배포를 특수 처리](../../extensibility/internals/handling-specialized-deployment.md)  
 프로젝트 하위 형식이 구현 하 여 특수 한 배포 동작을 제공할 수는 방법에 대해 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 인터페이스입니다.  
  
 [추가 하 고 속성 페이지를 제거 합니다.](../../extensibility/adding-and-removing-property-pages.md)  
 추가 하 고 프로젝트 디자이너의 속성 페이지를 제거에 대해 설명 합니다.  
  
## 관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 항목을 자세히 나타내는 링크를 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트입니다.
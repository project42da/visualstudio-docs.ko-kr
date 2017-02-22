---
title: "배포 프로젝트 형식 | Microsoft Docs"
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
  - "프로젝트 [Visual Studio SDK] 관리 코드"
  - "프로젝트 [Visual Studio SDK], 집계"
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 배포 프로젝트 형식
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 새 프로젝트 형식 집계 \(ProjectAggregator2.dll\) 및 재배포 \(ProjectAggregator2.msi\)에 대 한 Windows Installer 패키지를 설치합니다. 관리 코드 프로젝트 형식에 대 한 새 집계를 사용 해야 합니다. ProjectAggregator2 방법을 제한에서 작동 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 관리 코드 프로젝트 형식을 올바르게 작동 하지 못하도록 하는 집계 합니다. 다음 단계에는 새 집계를 사용 하 여 VSPackage를 변경 하는 방법을 설명 합니다.  
  
1.  솔루션에서 NativeHierarchyWrapper 프로젝트를 제거 합니다.  
  
2.  설치 프로그램에서 NativeHierarchyWrapper 이진 파일을 제거 합니다.  
  
3.  ProjectAggregator2.msi 설치에 추가 합니다.
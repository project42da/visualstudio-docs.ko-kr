---
title: "프로젝트 형식 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2171a940951d828df358d09dae5fec68b6475e4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-project-types"></a>배포 프로젝트 형식
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]새 프로젝트 형식 aggregator (ProjectAggregator2.dll) 및 재배포 (ProjectAggregator2.msi)에 대 한 Windows Installer 패키지를 설치합니다. 관리 코드 프로젝트 형식에 대 한 새 집계를 사용 해야 합니다. ProjectAggregator2 방법 제한에서 작동 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aggregator 관리 코드 프로젝트 형식을 올바르게 작동 하지 못하게 하는 프로젝트입니다. 다음 단계에서는 새 집계를 사용 하 여 VSPackage를 변경 하는 방법에 설명 합니다.  
  
1.  솔루션에서 NativeHierarchyWrapper 프로젝트를 제거 합니다.  
  
2.  설치 프로그램에서 NativeHierarchyWrapper 이진 파일을 제거 합니다.  
  
3.  ProjectAggregator2.msi 설치에 추가 합니다.
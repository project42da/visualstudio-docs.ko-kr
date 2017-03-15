---
title: "RegPkg 패키지 등록 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "RegPkg"
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# RegPkg 패키지 등록 문제 해결
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  .Pkgdef 파일을 사용 하 여를 Visual Studio에서 패키지를 등록 하는 것이 좋습니다. 따라서 확장 배포에 대 한 시스템 레지스트리에 액세스 하지 않고 있습니다. 사용 하 여 Pkgdef 파일이 생성 되는 [CreatePkgDef 유틸리티](../../extensibility/internals/createpkgdef-utility.md)합니다.  
  
 RegPkg를 사용 하 여 패키지를 등록 하려면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 패키지에 적합 한 RegPkg의 버전을 사용 해야 합니다.  
  
## 패키지 버전에 관련 된 RegPkg 버전  
 RegPkg의 두 가지 버전이 있습니다. 에 포함 된 하나의 버전 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 다음 어셈블리 중 하나를 사용 하 여 제공 된 패키지를 등록 하려면이 버전을 사용 합니다.  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 그 이전 Microsoft.VisualStudio.Shell.dll 어셈블리를 사용 하 여 제공 된 패키지를 등록할 수 없습니다.  
  
 이전 버전의 RegPkg Microsoft.VisualStudio.Shell.dll 어셈블리를 사용 하 여 제공 된 패키지를 등록할 수 있습니다. 그러나 그 해당 어셈블리의 이후 버전을 사용 하 여 작성 된 패키지를 등록할 수 없습니다.  
  
## 참고 항목  
 [제품 릴리스](../../misc/releasing-a-visual-studio-integration-product.md)
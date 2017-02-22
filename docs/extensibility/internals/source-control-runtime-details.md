---
title: "소스 제어에 대 한 런타임 세부 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK] 런타임 세부 정보"
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어에 대 한 런타임 세부 정보
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 또는 마법사와 같은 자동화 컨트롤러를 통해 파일이 프로젝트에 추가 하면 프로젝트를 소스 제어에 추가 됩니다.  프로젝트에 소스 제어 하에 있음을 지정 되지 않습니다. 소스 제어를 지원 하지만 수동으로 추가 해야 합니다.  
  
## 소스 제어 패키지를 등록 하는 중  
 소스 제어 프로젝트에 파일 추가 하면 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> 쿠키와 소스 제어 시스템에 의해 사용 되는 4 개의 불투명 문자열을 제공 합니다.  프로젝트 파일에서 이러한 문자열을 저장 합니다.  이러한 문자열 소스 제어 스텁 \(소스 제어 패키지를 관리 Visual Studio 구성 요소\) 프로젝트 형식의 시작 시 호출 하 여 전달 되어야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>.  이 차례로 적절 한 소스 제어 패키지를 로드 및 구현에 대 한 호출을 전달 합니다. `IVsSccManager2::RegisterSccProject`.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [소스 제어를 지원합니다.](../../extensibility/internals/supporting-source-control.md)
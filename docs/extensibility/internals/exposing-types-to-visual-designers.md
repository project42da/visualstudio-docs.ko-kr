---
title: "비주얼 디자이너 형식을 노출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a85648a95a6651ff62f50b2361b07feba9a58b47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-types-to-visual-designers"></a>비주얼 디자이너 형식을 노출합니다.
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]비주얼 디자이너를 표시 하기 위해 디자인 타임에 클래스 및 형식 정의에 액세스할 수 있어야 합니다. 클래스는 미리 정의 된 집합이 (참조 및 해당 종속성)은 현재 프로젝트의 전체 종속성 집합을 포함 하는 어셈블리에서 로드 됩니다. 또한 액세스 클래스 및 사용자 지정 도구에서 생성 된 파일에 정의 된 형식에 대 한 비주얼 디자이너에 필요한 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 시스템 임시 노트북을 통해 생성 된 클래스 및 형식에 액세스 하기 위한 지원을 제공 실행 파일 (임시 Pe). 사용자 지정 도구에 의해 생성 된 모든 파일 형식이 해당 어셈블리에서 로드 및 디자이너에 노출 될 수 있도록 임시 어셈블리로 컴파일할 수 있습니다. 각 사용자 지정 도구의 출력을 별도 임시 PE로 컴파일되고 성공 또는 실패의 임시 컴파일이 생성된 된 파일을 컴파일할 수 여부에 의해 결정 됩니다. 프로젝트에 전체적으로 빌드되지 않을 수 있습니다, 경우에 개별 임시 Pe 디자이너에 사용할 수 수 있습니다.  
  
 프로젝트 시스템에는 이러한 변경 내용은 사용자 지정 도구를 실행 한 결과를 사용자 지정 도구의 출력 파일의 변경 내용 추적에 대 한 완벽 하 게 지원을 제공 합니다. 사용자 지정 도구를 실행할 때마다 새 임시 PE가 생성 하 고 적절 한 디자이너에 전송 됩니다.  
  
> [!NOTE]
>  백그라운드에서 발생 하는 임시 프로그램 실행 파일 생성 파일 때문에 오류가 없으면 컴파일이 실패 하는 경우 사용자에 게 보고 됩니다.  
  
 임시 PE 지원 기능을 활용 하는 사용자 지정 도구는 다음 규칙을 따라야 합니다.  
  
-   `GeneratesDesignTimeSource`레지스트리에서 1로 설정 되어야 합니다.  
  
     프로그램 실행 파일 컴파일 없음이 설정이 없으면 이루어집니다.  
  
-   전역 프로젝트 설정와 같은 언어로 생성 된 코드 여야 합니다.  
  
     임시 PE에 요청 된 확장으로 사용자 지정 도구 보고 하는 항목에 관계 없이 컴파일됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> 있는 `GeneratesDesignTimeSource` 레지스트리에 1로 설정 됩니다. 확장명은.vb,.cs 또는.jsl; 될 필요가 없습니다. 모든 확장 가능 합니다.  
  
-   사용자 지정 도구에 의해 생성 된 코드는 유효 해야 하 고 시간에 프로젝트에 있는 참조의 집합에만 사용 하는 자체 컴파일해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 실행을 완료 합니다.  
  
     임시 PE를 컴파일할 때 컴파일러에 제공 되는 유일한 소스 파일은 사용자 지정 도구 출력이 있습니다. 따라서 임시 PE를 사용 하는 사용자 지정 도구 프로젝트의 다른 파일과 별도로 컴파일할 수 있는 출력 파일을 생성 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BuildManager 개체 소개](http://msdn.microsoft.com/en-us/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [단일 파일 생성기를 구현합니다.](../../extensibility/internals/implementing-single-file-generators.md)   
 [단일 파일 생성기 등록](../../extensibility/internals/registering-single-file-generators.md)
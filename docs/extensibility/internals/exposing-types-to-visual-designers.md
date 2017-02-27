---
title: "비주얼 디자이너에 형식을 노출합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "비주얼 디자이너를 노출 하는 형식 [Visual Studio SDK]"
  - "형식을 노출 하는 디자이너 [Visual Studio SDK]"
  - "비주얼 디자이너에 형식을 노출 하는 사용자 지정 도구"
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 비주얼 디자이너에 형식을 노출합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]클래스 및 형식 정의를 디자인 타임에 비주얼 디자이너를 표시 하려면 권한이 있어야 합니다.  클래스는 미리 정의 된 집합 완료 의존 관계 집합 현재 프로젝트 \(종속성 참조\)을 포함 하는 어셈블리에서 로드 됩니다.  비주얼 디자이너에 대 한 필요한 액세스 클래스 및 사용자 지정 도구에서 생성 한 파일에 정의 된 형식으로 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 생성 된 클래스와 형식의 임시 노트북을 통해 액세스를 위한 지원을 제공할 프로젝트 시스템 실행 파일 \(임시 Pe\).  사용자 지정 도구에서 생성 된 파일 형식에서 해당 어셈블리를 로드 및 디자이너에 노출 될 수 있습니다 있도록 임시 어셈블리로 컴파일할 수 있습니다.  각 사용자 지정 도구의 출력 별도 임시 PE로 컴파일됩니다과 성공 또는 실패가 임시 컴파일만 여부 또는 생성 된 파일이 컴파일될 수에 따라 달라 집니다.  프로젝트 전체를 건설할 수 없습니다 경우에 개별 임시 Pe를 아직 디자이너에 사용할 수 있습니다.  
  
 사용자 지정 도구를 실행 하면 이러한 변경 되는 사용자 지정 도구의 출력 파일에 변경 내용을 추적 하는 데 완벽 하 게 지원 프로젝트 시스템을 제공 합니다.  사용자 지정 도구를 실행할 때마다 새 임시 PE가 생성 되 고 디자이너가 해당 알림 메시지를 보내도록 합니다.  
  
> [!NOTE]
>  임시 프로그램 실행 파일 생성 파일 백그라운드에서 수행 되므로 컴파일 오류가 발생 하면 오류 없이 사용자에 게 보고 됩니다.  
  
 임시 PE 지원을 활용 하는 사용자 지정 도구는 다음과 같은 규칙을 따라야 합니다.  
  
-   `GeneratesDesignTimeSource`레지스트리를 1로 설정 되어야 합니다.  
  
     프로그램 실행 파일 컴파일 없음이 설정 하지 않고 수행 됩니다.  
  
-   생성 된 코드를 동일한 언어로 글로벌 프로젝트 설정 해야 합니다.  
  
     임시 PE는 사용자 지정 도구는 요청 된 확장에서 보고에 관계 없이 컴파일됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> 는 `GeneratesDesignTimeSource` 를 1로 설정 됩니다.  확장명은.vb,.cs 또는.jsl 될 필요는 없습니다. 이 확장 될 수 있습니다.  
  
-   사용자 지정 도구에서 생성 한 코드는 유효 해야 하 고 자신의 프로젝트에 대 한 참조 집합 시간에 사용에 컴파일해야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> 완료를 실행 합니다.  
  
     임시 PE를 컴파일할 때 컴파일러에 제공 된 유일한 소스 파일 사용자 지정 도구 출력 됩니다.  따라서 임시 PE를 사용 하는 사용자 지정 도구와 독립적으로 다른 프로젝트의에서 파일을 컴파일할 수 있는 출력 파일을 생성 해야 합니다.  
  
## 참고 항목  
 [Introduction to the BuildManager Object](http://msdn.microsoft.com/ko-kr/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [단일 파일 생성기를 구현합니다.](../../extensibility/internals/implementing-single-file-generators.md)   
 [프로젝트의 기본 네임스페이스 확인](../../misc/determining-the-default-namespace-of-a-project.md)   
 [단일 파일 생성기를 등록 하는 중](../../extensibility/internals/registering-single-file-generators.md)
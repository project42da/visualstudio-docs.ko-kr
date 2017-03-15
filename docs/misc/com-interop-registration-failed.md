---
title: "COM Interop registration failed | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannot_register_com2"
ms.assetid: d1b81f8e-66d7-4cfc-96ff-f1436a8f854a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# COM Interop registration failed
COM 클라이언트에 기능을 노출하는 어셈블리를 등록할 수 없습니다.  이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
 어셈블리는 COM 클라이언트에 개체를 노출시킬 수 있습니다.  프로젝트 시스템에는 노출된 클래스를 COM interop에 등록할 뿐 아니라 형식 라이브러리를 생성하고 등록하여 Visual Basic 6과 같은 스크립트 언어에서 이러한 클래스를 사용할 수 있도록 하는 속성이 있습니다.  
  
 **COM Interop 등록** 속성에 액세스하려면 **구성 속성** 폴더의 **빌드** 속성 페이지를 참조하십시오.  
  
 등록 취소에 실패한 이유는 다음과 같습니다.  
  
-   어셈블리에 대한 형식 라이브러리를 생성할 수 없습니다.  디스크 공간에 문제가 있거나 Visual Studio나 다른 프로세스에서 형식 라이브러리를 잠그는 파일 잠금 문제가 있는 경우입니다.  참조된 어셈블리에 대한 형식 라이브러리를 시스템에 적절히 등록하지 않은 경우도 이에 해당합니다.  
  
-   생성된 형식 라이브러리를 등록할 수 없습니다.  레지스트리에 사용 권한 문제가 있을 때 실패합니다.  
  
-   어셈블리에 클래스를 등록할 수 없습니다.  레지스트리에 사용 권한 문제가 있을 때 실패합니다.  
  
 **이 오류를 해결하려면**  
  
-   컴퓨터에 사용 가능한 디스크 공간을 만듭니다.  
  
-   파일 잠금 문제가 있으면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작합니다.  
  
-   Administrator로 또는 레지스트리 액세스 권한이 있는 그룹의 구성원으로 로그온했는지 확인합니다.  
  
## 참고 항목  
 [COM Interoperability in .NET Framework Applications](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)
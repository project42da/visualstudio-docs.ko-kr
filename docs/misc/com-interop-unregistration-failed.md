---
title: "COM Interop unregistration failed | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannot_unregister_com2"
ms.assetid: 1172b560-c4b0-4aff-9f74-cf9b29ff76d9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# COM Interop unregistration failed
어셈블리의 이전 복사본을 등록 취소하려고 할 때 문제가 발생했습니다.  
  
 **COM Interop 등록** 속성이 설정되어 있으면 프로젝트 시스템에서는 방금 빌드한 복사본을 등록하기 전에 먼저 COM 개체의 이전 복사본의 등록을 취소하려고 합니다.  이는 레지스트리를 최신 상태로 유지하기 위한 것입니다.  
  
 **COM Interop 등록** 속성에 액세스하려면 구성 속성 폴더의 **빌드** 속성 페이지를 참조하십시오.  
  
 등록 취소에 실패한 이유는 다음과 같습니다.  
  
-   어셈블리에 대한 이전 형식 라이브러리를 등록 취소할 수 없습니다.  레지스트리에 사용 권한 문제가 있을 때 실패합니다.  
  
-   이전 어셈블리를 등록 취소할 수 없습니다.  레지스트리에 사용 권한 문제가 있을 때도 실패합니다.  
  
 등록 취소 프로세스가 실패하면 CoCreatable 개체에 대한 GUID뿐 아니라 모든 형식 라이브러리의 GUID가 누수될 수 있습니다.  그러나 전체 빌드 프로세스는 실패하지 않습니다.  
  
## 참고 항목  
 [COM Interoperability in .NET Framework Applications](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)
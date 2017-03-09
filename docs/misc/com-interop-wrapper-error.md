---
title: "COM Interop Wrapper Error | Microsoft Docs"
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
  - "vs.tasklisterror.cannotcopyassembly"
  - "Vs.refruntlbimp"
helpviewer_keywords: 
  - "COM Interop Wrapper dialog box"
ms.assetid: 9a9d6374-ee26-4dbc-9e34-e1d90f6254b4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# COM Interop Wrapper Error
이 메시지 상자는 프로젝트 시스템에서 특정 구성 요소에 대한 COM interop 래퍼를 만들 수 없을 경우에 나타납니다.  COM interop 래퍼는 CLR\(공용 언어 런타임\)에서 COM 구성 요소를 관리하고 이와 통신하는 데 필요합니다.  자세한 내용은 [Visual Basic 및 Visual C\#에서 COM 상호 운용성](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)을 참조하세요.  
  
 일반적으로 이 오류가 발생하는 이유는 다음과 같습니다.  
  
-   구성 요소에 대한 형식 라이브러리가 올바로 등록되어 있지 않습니다.  
  
-   래핑되는 구성 요소의 기반이 되는 구성 요소가 컴퓨터에 없습니다.  
  
 위와 같은 두 경우에, COM 구성 요소가 컴퓨터에 올바로 설치되고 등록되어 있는지 확인하여 재작업을 수행해야 합니다.  
  
> [!TIP]
>  [MSDN 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=3355)에서 특정 COM 구성 요소용으로 게시된 COM interop 래퍼를 검색할 수도 있습니다.  
  
> [!NOTE]
>  COM interop 래퍼는 "주 interop 어셈블리"라고도 합니다. 이러한 용어는 동의어입니다.  
  
## 참고 항목  
 [Visual Studio의 구성 요소 모델 네임스페이스](http://msdn.microsoft.com/ko-kr/705d0add-0707-44ba-a6de-637381d9c937)   
 [구성 요소 제작](../Topic/Component%20Authoring.md)   
 [COM Interop](/dotnet/visual-basic/programming-guide/com-interop/index)   
 [공용 언어 런타임](../Topic/Common%20Language%20Runtime%20\(CLR\).md)   
 [COM Interoperability in .NET Framework Applications](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications)